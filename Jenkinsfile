@Library('shared_lib') _

pipeline{
    agent any

    stages{

        stage("Git checkout"){

            steps{
                script{
                    gitCheckout(
                        branch: "master",
                        url:"https://github.com/vishaldurgule8832/java-cicd-complete-project.git"
                    )
                }
            }
        }
    }




}