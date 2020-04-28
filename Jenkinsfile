pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {

        stage('npm install') {
          sh 'npm install'
        }
         stage('webdriver update') {
          sh 'webdriver-manager update'
        }

        stage('Run test') {
          sh 'protractor conf.js'         
        }
    }
}