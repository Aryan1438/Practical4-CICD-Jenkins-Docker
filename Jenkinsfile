pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh '''
                    apt-get update
                    apt-get install -y python3 python3-pip
                    pip3 install --break-system-packages -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                sh 'python3 -m pytest test_app.py -v'
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }
        failure {
            echo 'CI/CD Pipeline failed.'
        }
    }
}
