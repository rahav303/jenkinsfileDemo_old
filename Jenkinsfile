pipeline{
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
 
    agent any
    
    stages{
        stage('Clone git repo')
        {
            steps{
                git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
            }
        }
        stage('Testing')
        {
            steps{
               sh 'mvn test'
            }
            post{
                success{
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage ('Coverage')
        {
            steps{
                sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
            }
        }
    }
}
