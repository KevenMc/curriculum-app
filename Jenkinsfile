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
            sh '''

 curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash && nvm install v18.14.1
&& node --version && cd curriculum-front && npm i && npm install --save-dev vue-jest&& npm run test:unit'''
          }
        }

      }
    }

  }
}