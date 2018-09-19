pipeline {
    stages {
        stage('Running stage against  master branch') {
            when {
                branch 'master' 
            }
            steps {
                docker run -it httpd
                docker run -d -p 8080:8080 pipeline/httpd
            }
        }
        stage('Running stage against Intergration branch') {
            when {
                branch 'Intergration'  
            }
            steps {
                docker build -t pipeline/httpd .
                docker run -it httpd
                docker run -d -p 8080:8080 pipeline/httpd
            }
        }
    }
}
