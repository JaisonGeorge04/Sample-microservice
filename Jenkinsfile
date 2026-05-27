pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/JaisonGeorge04/Sample-microservice.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                sudo apt update
                sudo apt install python3-pip -y
                pip3 install -r requirements.txt
                '''
            }
        }

        stage('Run Application') {
            steps {
                sh '''
                pkill -f app.py || true
                nohup python3 app.py > output.log 2>&1 &
                '''
            }
        }
    }
}
