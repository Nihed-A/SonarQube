pipeline{
    agent any
    environment {
        PATH = "$PATH:/opt/apache-maven-3.8.2/bin"
    }
    stages{
       stage('GetCode'){
            steps{
                git 'https://github.com/Nihed-A/SonarQube'
            }
         }        
       stage('Build'){
            steps{
                sh 'mvn clean package'
            }
         }
        stage('SonarQube analysis') {

        steps{
        withSonarQubeEnv('sonarqube-10.2.1') { 
 
        sh "mvn sonar:sonar"
    }
        }
        }
       
    }

}
