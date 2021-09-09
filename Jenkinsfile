pipeline {
  agent any
  tools { 
        maven 'maven'
    }
  stages {
    stage('Clone Down'){
      steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/amrutashety/sample-maven.git']]])
      }
    }

    stage('Build and code analysis'){      
      steps {
        sh "mvn clean install sonar:sonar -s settings.xml"
      }
    }
  }
  post {
    cleanup {
        deleteDir() /* clean up our workspace */
    }
  }
}
