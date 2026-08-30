pipeline {
    agent { label 'devops-challenge-node' }
    stages {
        stage('Checkout from the Github') {
            steps {
                git branch: 'main', url: 'https://github.com/gulshan01-devops/devops-challenge-task.git'
            }
        }
        stage('Deploy to the KIND Cluster') {
            steps {
                sh '''
                    cd ~/task1
                    kubectl apply -f mysql.yml
                    kubectl apply -f nginx.yml
                '''
            }
        }
    }
}
#test-change
