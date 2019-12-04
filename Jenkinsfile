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
     stage('Change directory') {
      steps {
        sh 'cd /home/webwerks/Calculator/'
      }
    } 
    stage('Build docker image') {
      steps {
         sh 'docker build -t priyankak1212/calculator Dockerfile'
      }
    } 
     stage('Run docker image') {
      steps {
         sh 'docker run -d -p 5050:7070 priyankak1212/calculator -it /bin/bash'
      }
    } 
  }
}
