//pipeline{

  //agent any
    
    
        //stages{
         
        //stage('Git Checkout'){
           // steps{
           // git branch: 'main', url: 'https://github.com/arunprabhavathi456/mrdevops_java_app.git'
           //}
            
        //}
            //stage('unit test'){
            //steps{
            //sh 'mvn test'
           //}
            
        //}
             //stage('Integration testing'){
            //steps{
             // sh 'mvn verify -DskipUnitTests'
           //}
            
        //}
           // stage('Static code analysis'){
            
            //steps{
               // withSonarQubeEnv('sonarqube-8.9.1') {
                //sh "mvn sonar:sonar"                             
                     
            // }
        
          //}
  
        //}
            //stage('maven build'){
            
            //steps{
                //sh "mvn clean install"                             
                     
             //}
        
          //}
            //stage('Build Docker Image') {         
           //steps{  
               //sh 'sudo docker build -t arunprabhavathi456/springboot:1.1 .'           
               //echo 'Build Image Completed'                
         //}           
     //}
  
  //}
    
//}

pipeline {  
    
  agent{      
    node { label 'node_js'}     
  }  
  environment {     
    DOCKERHUB_CREDENTIALS= credentials('Dockerhub')     
  }    
  stages {         
    stage("Git Checkout"){           
      steps{                
	git branch: 'main', url: 'https://github.com/arunprabhavathi456/springboot-webapplication.git'                
	echo 'Git Checkout Completed'            
      }        
    }
       stage('maven build'){
            
         steps{
                sh "mvn clean install"                             
                     
             }
        
          }
	  
    stage('Build Docker Image') {         
      steps{                
	sh 'sudo docker build -t arunprabhavathi456/arun_text:tagname .'           
        echo 'Build Image Completed'                
      }           
    }
    stage('Login to Docker Hub') {         
      steps{                            
	sh 'echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'                 
	echo 'Login Completed'                
      }           
    }               
    stage('Push Image to Docker Hub') {         
      steps{                            
	sh 'sudo docker push arunprabhavathi456/arun_text:tagname'                 
	      echo 'Push Image Completed'       
      }           
    }      
  } //stages 
  post{
    always {  
      sh 'docker logout'           
    }      
  }  
} //pipeline


  

