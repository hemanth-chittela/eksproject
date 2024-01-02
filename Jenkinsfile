pipeline {
    agent
    {
        label 'another node'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        
        stage('deleting the current workspace') {
            steps {
                        deleteDir()
                }
            }
        
        stage('cloning repository') {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/hemanth-chittela/eksproject.git'
         }
     }
     
     
     stage('terraform init') {
         steps{
                sh 'terraform init'
            }
        }
    stage('terraform plan') {
        steps{
                sh 'terraform plan'
            }
        }
    stage('terraform apply') {
        steps{
                    sh 'terraform apply -auto-approve'
                 }
            }
    stage('terraform destroy') {
            steps {
                    sh 'terraform destroy -auto-approve'
                  }
                }
            }
    
        }


     