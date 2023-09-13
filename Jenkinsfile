pipeline {
    agent any
    stages {
        stage('Fetch Code') {
            steps {
                // Check out your source code from your version control system (e.g., Git)
                git branch: 'main', url:'https://github.com/kaushik-prasad-dey/jenkins_mvn_repo.git'
            }
        }
        stage('Build') {
            steps {
                // Build your application here
                withMaven(maven: 'Maven3') {
                     sh "mvn install"
                }
            }
        }
        stage('Test') {
            steps {
                // Run your tests here
                withMaven(maven: 'Maven3') {
                    sh 'mvn test' // Example for a Maven project    
                }
            }
        }
    }
    post {
        success {
            // Send notifications or perform actions on successful build and deployment
            echo 'Build and deployment successful!'
        }
        failure {
            // Send notifications or perform actions on build or deployment failure
            echo 'Build or deployment failed!'
        }
    }
}
