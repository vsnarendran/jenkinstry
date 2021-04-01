pipeline {
    agent any
    stages {
        stage('Example Build') {
			agent { master }
            steps {
                echo 'Hello, Maven'
                bat 'mvn -version'
            }
        }
        stage('Example Test') {
		    agent{master}
            steps {
                echo 'Hello, JDK'
                bat 'java -version'
            }
        }
    }
}