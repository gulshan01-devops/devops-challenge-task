pipeline {
    agent any

    stages {
        stage('Checkout from the Github') {
            steps {
                git branch: 'main', url: 'https://github.com/gulshan01-devops/devops-challenge-task.git'
            }
        }

        stage('Deploy to the KIND Cluster') {
            steps {
                sshagent(['devops-challenge-node']) {
                    sh '''
                        ssh -o StrictHostKeyChecking=no ubuntu@54.83.113.88
                        cd ~/task1 &&
                        kubectl apply -f mysql.yml &&
                        kubectl apply -f nginx.yml
                        "
                    '''
                }
            }
        }
    }
}
