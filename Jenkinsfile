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
                sh './hello.bat'
            }
        }
        stage('HTML Validation') {
            steps {
                echo 'Running HTML Validation...'
                sh 'tidy -q -e index.html || echo "HTML issues detected!"'
            }
        }
    }
}
