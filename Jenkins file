pipeline {
	agent none
	stages {
		stage ('Non-Parallel stage') {
			agent {
				label "master"
				}
			steps {
				echo "This stage will be executed first"
				}
		}
		
		stage ('Run Test1') {
			parallel {
				stage ('Test on Windows') {
					agent {
						label "Windows_Node"
						}
					steps {
						echo "Task1 on agent"
						}
				}
				
				stage ('Test on Master') {
					agent {
						label "master"
					}
					steps {
						echo "Task1 on master"
					}
				}
			}
		}
	}
}
					
