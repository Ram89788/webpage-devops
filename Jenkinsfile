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
                run 'mvn clean install'  // Assuming your build script is called build.sh
            }
        }

        stage('Test') {
            steps {
                // Execute your test script if you have one
                echo 'Tested successfull'
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
