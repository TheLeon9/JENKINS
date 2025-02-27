pipeline {
    agent any

    environment {
        NODE_ENV = 'development'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Installing Node.js dependencies...'
                sh 'npm install'
                sh 'npm install -g mocha || true'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running unit tests...'
             
                sh 'chmod +x node_modules/.bin/mocha || true'
             
                sh 'node ./node_modules/mocha/bin/mocha.js test.js'
            }
        }

        stage('Build Project') {
            steps {
                echo 'Building the project...'
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application....'
             
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
    
        }
        failure {
            echo 'Pipeline execution failed!'
          
        }
    }
}
