pipeline{
    agent any
    
    stages{
        stage("CONTINOUS DOWNLOAD"){
            steps{
                git branch: 'main', url: 'https://github.com/jbpellicciapro/SIELI-CICD.git'
            }
        }
        stage("Unit Test"){
            steps{
                sh'mvn test'
            }
        }
    }

}