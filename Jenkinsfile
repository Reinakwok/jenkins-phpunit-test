pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                bat 'composer install'
            }
        }
        stage('Test') {
            steps {
                bat './vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
            }
        }
    }
    post {
        always {
            junit testResults: 'logs/unitreport.xml'
        }
    }
}
