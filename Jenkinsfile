pipeline {
    agent none 
    stages {
        stage('Example Build') {
            steps {
                echo 'Hello, Maven'
                cmd 'mvn --version'
            }
        }
        stage('Example Test') {
            steps {
                echo 'Hello, JDK'
                cmd 'java -version'
            }
        }
    }
}