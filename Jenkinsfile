pipeline {
  agent any
  stages {
    stage('f') {
      parallel {
        stage('f') {
          steps {
            sh '''pipeline {
    agent any
    stages {
        stage(\'Test\') {
            steps {
                sh \'./gradlew check\'
            }
        }
    }
    post {
        always {
            junit \'build/reports/**/*.xml\'
        }
    }
}'''
            }
          }
          stage('error') {
            steps {
              sh '''
#!/bin/bash

# example of using arguments to a script
echo "My first name is $1"
echo "My surname is $2"
echo "Total number of arguments is $#" '''
            }
          }
        }
      }
    }
  }