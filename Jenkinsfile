pipeline {
  agent none
  options {
   timeout(time: 10, unit: 'MINUTES') 
  }
  stages {
    stage('maven') {
      agent { label 'maven' }
        steps {
            container ('mavencontainer') {
              sh 'mvn -Duser.home=/var/maven -V -q -e clean verify -Dmaven.test.failure.ignore'
              sh 'mvn -Duser.home=/var/maven -q test'
             }
          }
        }
      }
    }
