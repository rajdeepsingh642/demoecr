pipeline {
    
	agent any

   
    stages{
        
        stage('BUILD'){
            steps {
                sh 'printenv'
            }
            
        }

	      stage('Docker build'){
            steps {
                
                    sh 'docker build -t demoecr .'
                    
                }
            
            
        }

	     

    }
}
