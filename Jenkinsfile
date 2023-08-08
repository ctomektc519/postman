pipeline {
    agent any

    stages {
        stage('Checkout Git') {
            steps {
                git 'https://github.com/ctomektc519/postman'
            }
        }
        
                stage('Run tests') {
            steps {
                bat 'newman run komentarze.json -r htmlextra --reporter-htmlextra-export "test.html"'
            }
        }
        
                stage('Generate report') {
            steps {
                publishHTML([allowMissing: false, alwaysLinkToLastBuild: true, keepAll: true, reportDir: '', reportFiles: 'test.html', reportName: 'HTML Report', reportTitles: '', useWrapperFileDirectly: true])
            }
        }
    }
}
