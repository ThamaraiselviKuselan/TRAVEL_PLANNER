pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                sh """
                    ssh -o StrictHostKeyChecking=no ubuntu@15.135.219.82 '
                        cd /home/ubuntu/TRAVEL_PLANNER &&
                        git pull origin main &&
                        sudo docker-compose down &&
                        sudo docker-compose up -d --build
                    '
                """
            }
        }
    }
}
