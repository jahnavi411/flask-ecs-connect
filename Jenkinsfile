pipeline {
  agent any

  stages {
    stage('clone git repo') {
      steps {
        git branch: 'main', url: 'https://github.com/jahnavi411/flask-ecs-connect.git'
      }
    }
    
    stage('image building') {
      steps {
        sh "docker build -t flask-app ."
      }
    }
    
    stage('create container') {
      steps {
        sh "docker run -d -p 80:80 flask-app"        
      }
  }
 }
}
