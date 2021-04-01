pipeline {
    agent any
    stages {
        stage('Example Build') {
			agent { label 'master' }
            steps {
                echo 'Hello, Maven'
            }
        }
        stage('Example Test') {
			agent { label 'master' }
            steps {
                echo 'Hello, JDK'
            }
        }
    }
}