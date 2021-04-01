pipeline {
    agent none 
    stages {
        stage('Example Build') {
            steps {
                echo 'Hello, Maven'
                bat 'mvn -version'
            }
        }
        stage('Example Test') {
            steps {
                echo 'Hello, JDK'
                bat 'java -version'
            }
        }
    }
}