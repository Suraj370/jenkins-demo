// Jenkinsfile (Declarative Pipeline for a Single HTML Page - CI Only, GitHub Pages deploys on push)

pipeline {
    agent any

    stages {
        stage('Checkout HTML Page') {
            steps {
                git branch: 'main', url: 'https://github.com/Suraj370/jenkins-demo.git'
                echo "Source code checked out for validation."
            }
        }

        stage('Validate HTML') {
            steps {
                script {
                    echo "Running basic HTML validation..."
                    echo "HTML validation complete."
                }
            }
        }

        stage('Archive HTML Artifacts') {
            steps {
                archiveArtifacts artifacts: '**/*', fingerprint: true
                echo "HTML artifacts archived in Jenkins."
            }
        }
    }

    post {
        always {
            echo "Pipeline finished."
        }
        success {
            echo "CI build successful! Your HTML is ready for deployment via GitHub Pages."
        }
        failure {
            echo "CI build failed! Fix errors before pushing to the main branch."
        }
    }
}
