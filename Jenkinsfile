pipeline {
    agent any
    stages {
        stage('Build against master branch') {
            when {
                branch 'master'
            }
            steps {
                echo 'Hello World'
                sh '''docker ps '''
            }
        }
        stage('Build against feature branch') {
            when {
                branch 'feature-1'
            }
            steps {
                echo 'Deploying'
                sh ''' docker ps '''
            }
        }
    }
}
