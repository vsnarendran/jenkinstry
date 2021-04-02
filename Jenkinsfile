pipeline {
    agent any
	options { timestamps () }
    stages {
        stage('Build allScripts') {
			agent { label 'master' }
            steps {
                echo 'Calling build all Scripts'
				
            }
        }            
		stage('Build WithoutImporter Languages') {
			agent { label 'master' }
            steps {
                echo 'Calling build-languages-without-importer-dep'
	
            }
        }        
		stage('Build WithImporter Languages') {
			agent { label 'master' }
            steps {
                echo 'Calling build-languages-with-importer-dep'
            }
        }   
	stage('build') {
			parallel {			

					steps {
						echo 'Calling package-rcp'
					}       

					steps {
						echo 'Running build-and-run-tests'
						echo 'Running build-and-run-qaunit-tests'
						echo 'Running build-and-run-simulink-tests'
						echo 'Running build-and-run-analyses-tests'
					}
				}
			
			}
    }
}