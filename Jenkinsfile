pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {

        stage('npm install') {
             steps {
          sh 'npm install -g protractor'
             }
        }
         stage('webdriver update') {
              steps {
          sh 'webdriver-manager update'
              }
        }

        stage('Run test') {
             steps {
          sh 'protractor conf.js'   
             }      
        }
    }
}