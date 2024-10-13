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
                echo 'Updating Gradle Wrapper'
                sh './gradlew wrapper --gradle-version 7.5'

                echo 'Running build automation'
                sh './gradlew build --no-daemon'
            }
        }
    }
}
