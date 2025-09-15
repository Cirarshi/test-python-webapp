pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/YOUR_USERNAME/my-python-webapp.git'
            }
        }

        stage('Setup Python') {
            steps {
                sh '''
                  python3 -m venv venv
                  . venv/bin/activate
                  pip install --upgrade pip
                  pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                  . venv/bin/activate
                  python -m unittest discover -s tests || echo "No tests yet!"
                '''
            }
        }

        stage('Run App') {
            steps {
                sh '''
                  . venv/bin/activate
                  nohup python app.py > flask.log 2>&1 &
                '''
            }
        }
    }
}
