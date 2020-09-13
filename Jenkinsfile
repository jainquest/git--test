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
                when{
			{branch 'master'}
		     }
		steps{ echo "hello"}
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
				       image 'ubentu'
				}
			}
			steps{
			      echo "running inegration test"}
			}
            }
        }
    }
}
