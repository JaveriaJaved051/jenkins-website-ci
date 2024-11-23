pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/JaveriaJaved051/jenkins-website-ci'
            }
        }
        stage('Build Website') {
            steps {
                bat './hello.bat'
            }
        }
        stage('HTML Validation') {
            steps {
                echo 'Running HTML Validation...'
                // Use 'bat' to run HTML validation command in Windows
                bat 'tidy -q -e index.html || echo "HTML issues detected!"'
            }
        }
    }
}
