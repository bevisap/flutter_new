pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Flutter Version') {
            steps {
                bat 'C:\\flutter\\bin\\flutter.bat --version'
            }
        }

        stage('Get Dependencies') {
            steps {
                bat 'C:\\flutter\\bin\\flutter.bat pub get'
            }
        }

        stage('Analyze') {
            steps {
                bat 'C:\\flutter\\bin\\flutter.bat analyze'
            }
        }

        stage('Test') {
            steps {
                bat 'C:\\flutter\\bin\\flutter.bat test'
            }
        }

        stage('Build APK') {
            steps {
                bat 'C:\\flutter\\bin\\flutter.bat build apk --release'
            }
        }

        stage('Archive APK') {
            steps {
                archiveArtifacts artifacts: 'build\\app\\outputs\\flutter-apk\\app-release.apk',
                             fingerprint: true
            }
        }
    }
}



