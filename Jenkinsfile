pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out the code from the repository
                git url: 'https://github.com/rasyidk/testjenkins.git', branch: 'main'
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the index.html to /var/www/html/jen/
                script {
                    def targetDir = '/var/www/html/jen'
                    sh """
                        sudo mkdir -p ${targetDir}
                        sudo cp index.html ${targetDir}/
                    """
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment succeeded!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
