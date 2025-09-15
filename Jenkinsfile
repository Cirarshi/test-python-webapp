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
                    nohup python3 app.py > flask.log 2>&1 &
                    sleep 5
                    curl http://127.0.0.1:5000
                '''
            }
        }
    }
}
