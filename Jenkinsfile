pipeline {
  agent any
  stages {
    stage('Clone Down'){
      steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/amrutashety/sample-maven.git']]])
      }
    }

    stage('Push Docker App'){      
      steps {
        echo "build"
      }
    }
  }
  post {
    cleanup {
        deleteDir() /* clean up our workspace */
    }
  }
}