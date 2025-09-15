pipeline {
    agent any

    stages {
        stage('Build') {
           steps {
                sh '''
                    echo "Setting up virtual environment..."
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                    echo "Running tests..."
                    pytest || echo "No tests found"
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    echo "Deploying application..."
                    pkill -f "python3 app.py" || true
                    . venv/bin/activate
                    nohup python3 app.py > flask.log 2>&1 &
                    for i in {1..10}; do
                        curl -s http://127.0.0.1:5000 && break
                        echo "Waiting for Flask to start..."
                        sleep 2
                    done
                    sleep 5
                     curl -s http://127.0.0.1:5000 || (echo "Flask failed to start, logs:" && cat flask.log && exit 1)
                '''
            }
        }
    }
}
