pipeline {
  agent any
  stages {
    stage('Test') {
      parallel {
        stage('Maven') {
          steps {
            echo 'Running from Jenkins file'
            bat(script: 'mvn compile', label: 'Maven Install', returnStatus: true, returnStdout: true)
          }
        }

        stage('Cucumber') {
          steps {
            cucumber '**/*.json'
          }
        }

      }
    }

  }
}