pipeline {
    agent any
	options { timestamps () }
    stages {
			stage('build languages') {
                    steps {
                        script {
                            bash'''#!/bin/bash 
							cd code/languages
							ant csd-clean-and-build
                            '''
						}
                    }
                }
        stage('single run') {
            parallel {
                stage('Parallel Test 1') {
                    steps {
                        script {
                            def group1 = [:]
                            group1["build_languages"] = {
								
                                sh(script: "ant csd-clean-and-build")
                                
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