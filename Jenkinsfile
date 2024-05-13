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
    }

}