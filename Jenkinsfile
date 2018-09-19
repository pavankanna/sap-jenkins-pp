stage('Building against master') {
    when {
         branch 'master'
    }
    steps {
		docker run -it httpd
                docker run -d -p 8080:8080 pipeline/httpd
    }
}

stage('Building against master') {
    when {
         branch 'Intergration'
    }
    steps {
		docker build -t pipeline/httpd .
		docker run -it httpd
                docker run -d -p 8080:8080 pipeline/httpd
    }
}
