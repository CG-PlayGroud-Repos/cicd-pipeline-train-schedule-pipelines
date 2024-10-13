pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
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

