pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sh """
                    ssh -o StrictHostKeyChecking=no ubuntu@3.106.126.166 '
                        cd /home/ubuntu/TRAVEL_PLANNER &&
                        git pull origin main &&
                        sudo docker-compose down &&
                        sudo docker-compose build --no-cache &&
                        sudo docker-compose up -d
                    '
                """
            }
        }
    }
}
