pipeline {
    
    agent none
    
   stages {
        
        stage('Build'){
            
            agent {
                label "myslavemaven"
            }
          
          steps {
             
                echo "my master branch"
          }

        stage('SonarQube-Analysis'){
             scripts{
                 withSonarQubeEnv(cridentialsId:'jenkins-sonarqube-token'){
                     sh 'mvn sonar:sonar'
                 }
             }
          }
        }
   }
}
