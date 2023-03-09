pipeline {
  agent any
  tools {
    maven 'Maven' 
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat8(credentialsId: 'deployer', path: '', url: 'http:/3.101.88.23:8080/')], contextPath: '', onFailure: false, war: '*/.war' 
        }
      }
    }
  }
}
