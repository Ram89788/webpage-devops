pipeline {
    agent any

    triggers {
        // GitHub or GitLab webhooks will trigger this
        pollSCM('* * * * *')  // Optional: polling interval (every minute in this case)
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from version control
                git branch: 'main', url: 'https://github.com/Ram89788/webpage-devops.git'
            }
        }

        stage('Build') {
            steps {
                // Execute your build script
                sh './build.sh'  // Assuming your build script is called build.sh
            }
        }

        stage('Test') {
            steps {
                // Execute your test script if you have one
                sh './test.sh'
            }
        }

        stage('Deploy') {
            steps {
                // Optionally deploy your application after build
                sh './deploy.sh'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed. Check the logs for details.'
        
    }
}
}
