pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/JaveriaJaved051/jenkins-website-ci.git', branch: 'master'
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
                bat 'tidy -q -e index.html || echo "HTML issues detected!"'
            }
        }
    }
}
