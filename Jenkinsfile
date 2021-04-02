pipeline {
    agent any
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
		stage('package and run test parallely') {
				def stagess = [:]

				stagess["Package Languages"] = {
					echo "Calling package-rcp"
				}
				stagess["Run Test - one by one"] = {
					echo 'Running build-and-run-tests'
					echo 'Running build-and-run-qaunit-tests'
					echo 'Running build-and-run-simulink-tests'
					echo 'Running build-and-run-analyses-tests'
				}

				parallel(stagess)
			}		
		
    }
}