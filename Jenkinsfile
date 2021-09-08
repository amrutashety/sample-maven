pipeline {
  agent any
  tools { 
        maven 'maven3.6' 
        jdk 'jdk11' 
    }
  stages {
    stage('Clone Down'){
      steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/amrutashety/sample-maven.git']]])
      }
    }

    stage('Push Docker App'){      
      steps {
        sh "mvn clean install sonar:sonar"
      }
    }
  }
  post {
    cleanup {
        deleteDir() /* clean up our workspace */
    }
  }
}