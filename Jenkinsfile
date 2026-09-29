pipeline {
    agent any

    stages {

        stage('Flutter Version') {
            steps {
                bat 'C:\\src\\flutter\\bin\\flutter.bat --version'
            }
        }

        stage('Get Dependencies') {
            steps {
                bat 'C:\\src\\flutter\\bin\\flutter.bat pub get'
            }
        }

        stage('Analyze') {
            steps {
                bat 'C:\\src\\flutter\\bin\\flutter.bat analyze'
            }
        }

        stage('Test') {
            steps {
                bat 'C:\\src\\flutter\\bin\\flutter.bat test'
            }
        }

        stage('Build Web') {
            steps {
                bat 'C:\\src\\flutter\\bin\\flutter.bat build web --release'
            }
        }

        stage('Archive Web Build') {
            steps {
                archiveArtifacts artifacts: 'build\\web\\**',
                                 fingerprint: true
            }
        }
    }
}