pipeline {
    agent {
        docker {
            image 'python:3.9' // Use the appropriate Python Docker image
            args '-u root' // Optional: Run as root user if necessary
        }
    }

    environment {
        VIRTUALENV_NAME = 'venv'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/vamsi676/Python', branch: 'master'
            }
        }

        stage('Setup') {
            steps {
                sh 'python -m venv ${VIRTUALENV_NAME}'
                sh './${VIRTUALENV_NAME}/bin/pip install -r requirements.txt'
            }
        }
    }
}
