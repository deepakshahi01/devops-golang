pipeline{
	agent any
	tools{
		go 'go1.23.10'
	}
	stages{
		stage("build"){
			steps{
				sh '''
				mkdir -p build
				go build -o build/calculator
				'''
				echo "biuilding"
			}
		}
		stage("test"){
			steps{
				sh "go test ./..."
				echo "testing"
			}
		}
		stage("lint"){
			steps{
                                echo "linting"
                        }
		}
		stage("Arhieve"){
			steps{
				archieveArtifacts artifacts:"build/calculator*", fingerprint:true
			}
		}
		stage("deploy"){
			steps{
				echo "deploying"
			}
		}
	}
}
		
