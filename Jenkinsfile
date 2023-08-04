@Library('shared_lib') _

pipeline{
    agent any

    parameters{
        choice(name:'action',choice:'create/destroy',description:'choose what do you want')
    }

    stages{

        stage("Git checkout"){
            when{expression{parameters.action==create}}
            steps{
                script{
                    gitCheckout(
                        branch: "master",
                        url:"https://github.com/vishaldurgule8832/java-cicd-complete-project.git"
                    )
                }
            }
        }

        stage("Unit Testing"){
            when{expression{parameters.action==create}}
            steps{
                script{
                    
                    mvnTest()
                }
            }
        }

        stage("Integration test"){
            when{expression{parameters.action==create}}
            steps{
                script{
                    
                    mvnIntegrationTest()
                }
            }
        }
    }
}