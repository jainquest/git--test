pipeline {
    agent any
    stages {
        stage('one') {
            steps {
                echo "hi i am jain"
            }
        }
	stage('two') {
            steps {
                input("do you want to proceed")
            }
        }
	stage('three') {
            steps {
                echo "when is not working"
            }
        }
	stage('four') {
            parallel{
		stage("unittest"){
			steps{echo "running unit test"}
				}
		stage("inegration test"){
			agent{
				docker{
				       reuseNode flase
				       image 'ubuntu'
				}
			}
			steps{
			      echo "running inegration test"}
			}
            }
        }
    }
}
