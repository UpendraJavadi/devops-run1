pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    sudo cp index.html /var/www/html/index.html
                    sudo systemctl restart nginx
                '''
            }
        }
    }

    post {
        success {
            echo 'HTML deployment completed successfully!'
        }

        failure {
            echo 'HTML deployment failed!'
        }
    }
}

