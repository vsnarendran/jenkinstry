pipeline {
	agent("master") {
	stages
	{ 
		timeout(unit: 'SECONDS', time: 5) {
			stage("One"){
				sleep 10
				echo 'hello'
			}
		}
	}
}
}