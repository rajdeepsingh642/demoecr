pipeline {
    
	agent any

   
    stages{
        
        stage('BUILD'){
            steps {
                sh 'printenv'
            }
            
        }

	      stage('Publish ECR'){
            steps {
                withEnv {["AWS_ACCESS_KEY_ID=${env.AWS_ACCESS_KEY_ID}","AWS_SECRET_ACCESS_KEY=${env.AWS_SECRET_ACCESS_KEY}","AWS_DEFAULT_REGION=${env.AWS_DEFAULT_REGION}"]} {
                    sh 'docker login -u AWS -p ${aws ecr get-login-password --region ap-northeast-1} 429304386426.dkr.ecr.ap-northeast-1.amazonaws.com'
                    sh 'docker build -t demoecr .'
                    sh 'docker tag demoecr:latest 429304386426.dkr.ecr.ap-northeast-1.amazonaws.com/demoecr:""$BUILD_ID""'
                    sh 'docker push 429304386426.dkr.ecr.ap-northeast-1.amazonaws.com/demoecr:""$BUILD_ID""'
                    
                }
            
            }
        }

	     

    }
}
