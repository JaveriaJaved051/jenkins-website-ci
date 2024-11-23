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
                script {
                    if (isUnix()) {
                        sh './hello.sh'  // Use shell script for Linux
                    } else {
                        bat './hello.bat'  // Use batch script for Windows
                    }
                }
            }
        }
        stage('HTML Validation') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'tidy -q -e index.html || echo "HTML issues detected!"'  // Linux command
                    } else {
                        bat 'tidy -q -e index.html || echo "HTML issues detected!"'  // Windows command
                    }
                }
            }
        }
    }
}
