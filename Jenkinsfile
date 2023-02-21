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
            sh '''  sudo apt update && sudo apt install curl && sudo curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt install nodejs     && node --version && cd curriculum-front && npm i && npm install --save-dev vue-jest && npm run test:unit'''
          }
        }

      }
    }

  }
}