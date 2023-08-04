@Library('shared_lib') _

pipeline{
    agent any

    parameter{
        choice(name:'action',choice:'create/destroy',description:'choose what do you want')
    }

    stages{

        stage("Git checkout"){
            when{expression{parameter.action==create}}
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
            when{expression{parameter.action==create}}
            steps{
                script{
                    
                    mvnTest()
                }
            }
        }

        stage("Integration test"){
            when{expression{parameter.action==create}}
            steps{
                script{
                    
                    mvnIntegrationTest()
                }
            }
        }
    }
}