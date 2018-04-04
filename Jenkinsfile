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
          stage('') {
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
          }
        }
      }
    }