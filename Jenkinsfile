pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git "https://github.com/Suraj370/jenkins-demo.git"
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'No build steps needed for HTML.'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying HTML page...'

                sh 'cp index.html /var/www/html/'

      
            }
        }
    }

    post {
        success {
            echo 'Deployment completed successfully.'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
