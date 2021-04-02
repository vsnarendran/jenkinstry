pipeline {
    agent any
    stages {
        stage('Build Languages') {
			agent { label 'master' }
            steps {
                echo 'Hello, Maven'
            }
        }
        stage('Run Test') {
			agent { label 'master' }
            steps {
                echo 'Hello, JDK'
            }
        }
    }
}