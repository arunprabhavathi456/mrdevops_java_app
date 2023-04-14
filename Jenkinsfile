pipeline{

    agent any
    
    
        tages{
         
        stage('Git Checkout'){
            steps{
            git branch: 'main', url: 'https://github.com/arunprabhavathi456/mrdevops_java_app.git'
           }
            
        }
            stage('unit test'){
            steps{
            sh 'mvn test'
           }
            
        }
             stage('Integration testing'){
            steps{
              sh 'mvn verify -DskipUnitTests'
           }
            
        }
            stage('Static code analysis'){
            
            steps{
                withSonarQubeEnv('sonarqube-8.9.1') {
                sh "mvn sonar:sonar"                             
                     
             }
        
          }
  
        }
            stage('maven build'){
            
            steps{
                sh "mvn clean install"                             
                     
             }
        
          }
  
        }
    }  
  

