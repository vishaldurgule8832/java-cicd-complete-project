@Library('shared_lib') _

pipeline{
    agent any

    parameters{
        choice(name: 'action', choices:'create\ndelete', description: 'choose what do you want')
    }

    stages{

        stage('Git checkout'){
            when { expression { params.action=='create' } }
            steps{
                script{
                    gitCheckout(
                        branch: "master",
                        url:"https://github.com/vishaldurgule8832/java-cicd-complete-project.git"
                    )
                }
            }
        }

        stage('Unit Testing'){
            when { expression { params.action=='create' } }
            steps{
                script{
                    
                    mvnTest()
                }
            }
        }

        stage('Integration test'){
            when { expression { params.action=='create' } }
            steps{
                script{
                    
                    mvnIntegrationTest()
                }
            }
        }
        stage('StaticCode'){
            when { expression { params.action=='create' } }
            steps{
                script{
                    
                    def credentialsId= 'sonarqube-api'
                    statiCodeAnalysis(credentialsId)
                }
            }
        }
    }
}