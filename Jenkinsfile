pipeline {
    node('master') {
    stages {
        stage('Running stage against  master branch') {
            when {
                branch 'master' 
            }
            steps {
                docker run -d -p 8080:8080 pipeline/httpd
            }
	   steps {
		docker ps  | grep -v grep | grep httpd	
	   }
        }
        stage('Running stage against Intergration branch') {
            when {
                branch 'Intergration'  
            }
            steps {
                docker build -t pipeline/httpd .
            }
        }
	 stage('Running stage against Intergration branch') {
            when {
                branch 'Pull Request'
            }
            steps {
                docker build -t pipeline/httpd .
		docker run -d -p 8080:8080 pipeline/httpd
		docker ps  | grep -v grep | grep httpd
            }
        }

    }
  }
}
