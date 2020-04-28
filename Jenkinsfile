pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {

        stage('Build') {
          sh 'npm install'
        }
         stage('Build') {
          sh 'webdriver-manager update'
        }

        stage('Run Unit Tests') {
          sh 'protractor conf.js'         
        }
    }
}