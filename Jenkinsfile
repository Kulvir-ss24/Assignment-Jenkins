pipeline {
    agent any
    
    triggers {
        pollSCM('H/2 * * * *')
    }
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out your code...'
            }
        }
        stage('Build') {
            steps {
                echo 'Building your demo-pipeline project...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running final tests...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying your pipeline soon....Creating Image!'
                echo 'Building Docker image...'
                bat 'docker build -t pipeline-demo:latest .'
                
                echo 'Running Docker container...'
                bat 'docker run -d --name pipeline-demo-container pipeline-demo:latest'
                
                echo 'Docker deployment completed!'
            }
        }
    }
}

