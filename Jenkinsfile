pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                // Explicitly checkout the master branch
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/master']],
                    doGenerateSubmoduleConfigurations: false,
                    extensions: [],
                    userRemoteConfigs: [[url: 'https://github.com/CG-PlayGroud-Repos/cicd-pipeline-train-schedule-pipelines.git']]
                ])
            }
        }
        stage('Build') {
            steps {
               echo "code is building"
            }
        }
        stage('Deployment stage') {
            steps {
               echo "code is deploying"
                sh 'sudo -u jenkins docker ps'
            }
        }
    }
}
