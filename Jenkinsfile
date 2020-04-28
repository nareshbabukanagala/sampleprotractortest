pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {

    stage("Download GIT Code") {
        steps {
            script {
                try {
                   // -- Download GIT Code 
                    echo "Downloading GIT Code from: ${JOB_GIT_URL}. Branch: ${JOB_GIT_BRANCH}"
                    checkout([$class: "GitSCM", branches: [[name: "${JOB_GIT_BRANCH}"]], doGenerateSubmoduleConfigurations: false, 
                    extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: "${env.GIT_CREDENTIAL}", 
                    url: "${JOB_GIT_URL}"]]])
                } catch (err) { 
                    echo "The Download GIT Code Stage failed"                                          
                }
            }   
        }
    }
      
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