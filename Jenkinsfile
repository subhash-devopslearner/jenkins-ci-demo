pipeline {
    agent any

    parameters {
        choice(
            name: 'ENV',
            choices: ['dev', 'test', 'prod'],
            description: 'Select deployment environment'
        )
        booleanParam(
            name: 'RUN_TESTS',
            defaultValue: true,
            description: 'Run tests or skip'
        )
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/subhash-devopslearner/jenkins-ci-demo.git'
            }
            
        }
        
        stage('Test') {
            when {
                    expression { params.RUN_TESTS == true }
            }
            steps {
                echo "Running tests for ${params.ENV}"
                sh 'echo Tests passed'
            }
        }
        
        stage('Build') {
            steps {
                echo "Building for ${params.ENV}"
                sh 'echo Build successful'
            }
        }
        
        stage('Deploy'){
            steps {
                sh """
                sudo mkdir -p /var/lib/jenkins/deploy/${params.ENV}
                sudo cp index.html /var/lib/jenkins/deploy/${params.ENV}/index.html
                """
            }
        }
    }
}
