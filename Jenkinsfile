pipeline{
    agent any
    stages{
        stage("Maven Test"){
            steps{
                echo "Test"
            }
        }
        stage("Maven Build"){
            steps{
                echo "Build"
            }
        }
        stage("Maven Deploy"){
            steps{
                echo "Deploy jar to server"
            }
        }
    }
    post{
        success{
             echo "BUILD kar"
        }                
    }
}
