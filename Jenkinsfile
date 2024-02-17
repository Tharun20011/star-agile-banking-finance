pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git url: 'https://github.com/Tharun20011/star-agile-banking-finance.git'
                echo 'Git code is cloned'
            }
        }
      stage('Maven clean') {
            steps {
                sh 'mvn clean'
            }
        }
      stage('Maven package') {
            steps {
               sh 'mvn package'
            }
        }
      stage('Docker Image') {
            steps {
                sh 'docker build -t bankingimg . '
            }
        }
      stage('Docker deploy') {
            steps {
                sh 'docker run -d --name bankingcon -p 6543:8080 bankingimg '
            }
        }
    }
}
