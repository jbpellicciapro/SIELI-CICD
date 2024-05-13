pipeline{
    agent any
    
    stages{
        stage("CONTINOUS DOWNLOAD"){
            steps{
                git branch: 'main', url: 'https://github.com/jbpellicciapro/SIELI-CICD.git'
            }
        }
        stage("UNIT TEST"){
            steps{
                sh 'mvn test'
            }
        }
        stage("INTERGRATION TEST"){
            steps{
                sh 'mvn verify -DskipUnitTests'
            }
        }
        stage("CONTINOUS BUILD"){
            steps{
                sh 'mvn clean install'
            }
        }

        stage("STATIC TEST ANALISYS"){
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token'){
                        sh 'mvn clean package sonar:sonar'
                    }   
                }
                
            }
        }
        stage("CONTINOUS DELIVERY"){
            steps{
                script{
                    sh 'cp -r /home/ubuntu/.jenkins/workspace/test/ /var/www/html/'  
                }
                
            }
        }      
    }

}