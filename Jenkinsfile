pipeline{
    agent{
        docker {
                image 'maven'
                args '-v $HOME/.m2:/root/.m2'
                }
    }
    stages{
        stage("Quality Gate Statuc Check"){
            steps{
                      script{
                      withSonarQubeEnv(credentialsId: 'sonar-token') { 
                      sh "mvn sonar:sonar"
                       }
                      
		    sh "mvn clean install"
                  }
                } 
            }
         
        }
    
  
}
