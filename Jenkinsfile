pipeline {
  agent any
  stages {
        
    stage('Cloning Git') {
      steps {
        git 'https://github.com/priyankak1212/Calculator.git'
      }
    }
 
    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
     
    stage('Start') {
      steps {
         sh 'npm test'
      }
    }  
   
    stage('Build docker image') {
      steps {
         sh 'docker build -t priyankak1212/calculator .'
      }
    } 
     stage('Run docker image') {
      steps {
         sh 'docker run -p 49160:8080 -d priyankak1212/calculator'
      }
    } 
  }
}
