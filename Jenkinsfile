pipeline{
	agent{
		label 'slave2'
	}
	stages{
		stage('1-clone'){
			steps{
				sh 'cat /etc/passwd'
			}
		}
	stage('2-parallel-jobs'){
		parallel{
			stage('1-subjob1'){
				agent{
					label 'slave3'
				}
				steps{
					sh 'lscpu'
				}
			}
		stage('2-subjob-1'){
			when {
				branch 'feature'
			}
			steps{
				sh 'df -h'
			}
		}	
		}
	}	
	}
}
