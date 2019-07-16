Jenkinsfile (Declarative Pipeline)

pipeline {
    agent { docker { image 'python:3.5.1' } }
    stages {
        stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      //git 'https://github.com/Rajneesh13/flaskapp.git'
     //deleteDir()
     //sh "flaskapp"
      
      
     // if (!fileExists("flaskapp/Dockerfile")) {
      //   error('Dockerfile missing.')
    //  }
   }
   
   stage('Unit Test') {
      // run the unit tests
      dir("flaskapp") {
         
         sh "pip install -r requirements.txt"
        
      }
   }
   
   stage('Run') {
       // build the docker image from the source code using the BUILD_ID parameter in image name
       dir("flaskapp") {
         sh "docker-compose stop"
	     sh "docker-compose rm -f -v "
         sh "docker-compose build && docker-compose up -d"
       }
         
       }
    }
}

