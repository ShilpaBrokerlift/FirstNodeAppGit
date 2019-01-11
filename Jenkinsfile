pipeline {
    agent any
	    stages {
        	stage('One') {
            		steps {
                		echo 'This is the first step in the pipeline'
            		}
        	}
        	stage('Two') {
            		steps {
                		input('Do you want to proceed')
            		}
        	}
		stage('Three') {
		    when {
			    not {
				    branch "master"
			    }
		     }
		   steps {
			echo 'on master branch'
		    }
		}
	       stage('Four') {
			     parallel {
					stage('Unit Test') {
							steps{
								echo "Running the unit test..."						
							}
						}
					stage('Integration Test'){
								agent {
									docker {
										reuseNode false
										image 'ubuntu'
									}	
								}			
								steps {
									echo "Running integration test..."				
								}
							}
						}
					}

				}
    post {
        always {
            emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
        }
    }
}
