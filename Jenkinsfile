pipeline{

    agent any

        stages{
         
        stage('Git Checkout'){
            steps{
             git branch: 'main', url: 'https://github.com/arunprabhavathi456/mrdevops_java_app.git'
                }
           }
            stage('Unit test maven'){
            steps{
             sh 'mvn test'
                }
           }
      }
  
 }
         
