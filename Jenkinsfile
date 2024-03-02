pipeline {
    agent any
    
    environment {
        SERVICE_NAME = "Flo-Shopping-Cart-App"
        ORGANIZATION_NAME = "adedapoflorence"
        DOCKERHUB_USERNAME = "florence237"
        REPOSITORY_TAG = "${DOCKERHUB_USERNAME}/${ORGANIZATION_NAME}-${SERVICE_NAME}:${BUILD_ID}"
    }
   
    stages {
            
            
        stage ('Build and Push Image') {
            steps {
                 sh 'printenv'
                 withDockerRegistry([credentialsId: 'docker-hub', url: ""]) {
                   sh 'docker build -t ${REPOSITORY_TAG} .'
                   sh 'docker push ${REPOSITORY_TAG}'          
            }
          }
       }
    }  
