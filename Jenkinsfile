pipeline{

	agent any
	
		stages{
		
			stage('SCM checkout')
			{
				steps{
				
				git "https://github.com/TanumayDhar/openMRS_POM_model2.git"
					}
			}
			
			stage('Build')
			{
				steps{
					
					echo 'Building the application...'
				
				}
			
			}
			stage('Integration Test')
			{
				steps
				{
				
				bat 'mvn -f pom.xml clean install'
				
				}
			
			}
			
			
		
		}
		
		
			post {
			
				always 
				{
					
				step([$class: 'Publisher', reportFilenamePattern: '**/testng-results.html'])
				
				
				}
	
	
	}

}
