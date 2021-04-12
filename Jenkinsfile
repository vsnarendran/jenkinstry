pipeline {
    agent any
	options { timestamps () }
    stages {
		stage ('Git - Checkout csdplatform') {
			checkout scm:([$class: 'GitSCM', 
						branches: [[name: 'origin/$milestone']], 
						doGenerateSubmoduleConfigurations: false, 
						extensions: [], 
						submoduleCfg: [], 
						userRemoteConfigs: [url: 'http://ies-iesd-bitbucket.ies.mentorg.com/scm/csd/csdplatform.git']]) 
		}	
        stage('single run') {
            parallel {
                stage('Parallel Test 1') {
                    steps {
                        script {
                            def group1 = [:]
                            group1["test_1"] = {
                                echo "test_1"
                                sh(script: "echo 'vi'>scp.bat")
                                
                            }
                            group1["test_2"] = {
                                echo "test_2"
                                sh(script: "echo 'vi'>>scp.bat")
                            }
                            parallel group1
                        }
                    }
                }
                stage('Parallel Test 2') {
                    steps {
                        script {
                            def group2 = [:]
                            group2["test_3"] = {
                                echo "test_3"
                                sh(script: "echo 'vi'>>scp.bat")
                                
                            }
                            group2["test_4"] = {
                                echo "test_4"
                                sh(script: "date -u")
                                                            }
                            parallel group2
                        }
                    }
                }
            }
        }
		stage("scripting"){
				steps{
				script{
				sh(script: "more scp.bat")
				
					}
				}
				
		}
		
    }
}