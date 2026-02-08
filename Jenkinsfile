pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/subhash-devopslearner/jenkins-ci-demo.git'
            }
            
        }
        
        stage('Test') {
            steps {
                sh 'echo Running tests'
            }
        }
        
        stage('Build') {
            steps {
                sh 'echo Build successful'
            }
        }
        
        stage('Deploy'){
            steps {
                sh '''
                sudo mkdir -p /var/lib/jenkins/deploy
                sudo cp index.html /var/lib/jenkins/deploy/index.html
                '''
            }
        }
    }
}
