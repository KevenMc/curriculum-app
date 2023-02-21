pipeline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/KevenMc/curriculum-app.git', branch: 'main')
      }
    }

    stage('Log') {
      parallel {
        stage('Log') {
          steps {
            sh 'ls -la'
          }
        }

        stage('Front-end Unit test') {
          steps {
            sh '   node --version &&  cd curriculum-front && npm run test:unit'
          }
        }

      }
    }

  }
  tools {
    nodejs 'node'
  }
}