pipeline {
    agent any  // This tells Jenkins to run this pipeline on any available agent

    environment {
        // Define your environment variables here
        APP_DIR = 'app'  // Directory where your Symfony app is located
    }

    stages {
        stage('Preparation') {  // Get source code from SCM
            steps {
                checkout scm  // Checks out source code from the configured SCM repository
            }
        }

        stage('Install Dependencies') {
            steps {
                dir("${env.APP_DIR}") {  // Navigate to the app directory
                    sh 'composer install --no-interaction --prefer-dist'  // Install PHP dependencies
                }
            }
        }

        stage('Run Tests') {
            steps {
                dir("${env.APP_DIR}") {
                    sh './vendor/bin/phpunit'  // Run PHPUnit tests
                }
            }
        }

        stage('Build') {
            steps {
                dir("${env.APP_DIR}") {
                    // Add steps for any building tasks, like compiling assets
                    sh 'echo "Build steps go here"'
                }
            }
        }

        stage('Deploy to Staging') {
            when {
                branch 'develop'  // Only run this stage when on the 'develop' branch
            }
            steps {
                dir("${env.APP_DIR}") {
                    // Deployment scripts or commands to deploy to the staging environment
                    sh 'echo "Deploy to staging environment"'
                }
            }
        }

        stage('Deploy to Production') {
            when {
                branch 'master'  // Only run this stage when on the 'master' branch
            }
            steps {
                dir("${env.APP_DIR}") {
                    // Deployment scripts or commands to deploy to the production environment
                    sh 'echo "Deploy to production environment"'
                }
            }
        }
    }

    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
    }
}
