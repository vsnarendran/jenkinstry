pipeline {
    agent any
    stages {
        stage('Example Build') {
			agent { label 'master' }
            steps {
                echo 'Hello, Maven'
                bat 'mvn -version'
            }
        }
        stage('Example Test') {
			agent { label 'master' }
            steps {
                echo 'Hello, JDK'
                bat 'java -version'
            }
        }
    }
}