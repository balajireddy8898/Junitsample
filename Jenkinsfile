pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/balajireddy8898/Junitsample.git', branch: 'master')
      }
    }
    stage('compile') {
      steps {
        bat 'mvn compile'
      }
    }
    stage('JunitTest') {
      steps {
        bat 'mvn test'
      }
    }
    stage('Sonarqube') {
      steps {
        bat 'mvn sonar:sonar'
        bat 'mvn clean install'
      }
    }
    stage('deploy') {
      steps {
        bat 'xcopy "C:\\Program Files (x86)\\Jenkins\\workspace\\Junitsample_master\\target\\junitsample-0.0.1-SNAPSHOT.war" "C:\\Program Files\\Apache Software Foundation\\Tomcat 8.5\\webapps"'
      }
    }
  }
}