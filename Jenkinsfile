pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Cloning Repository'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                pip3 install flask --break-system-packages
                '''
            }
        }

        stage('Deploy Application') {
            steps {
                sh '''
                pkill -f app.py || true
                nohup python3 app.py > output.log 2>&1 &
                '''
            }
        }

    }
}
