pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build & Test') {
            steps {
                bat './gradlew test'
            }
        }

        stage('Package') {
            steps {
                bat './gradlew build'
		archiveArtifacts artifacts: 'app/build/libs/*.jar', fingerprint: true

            }

        }
    }
}
