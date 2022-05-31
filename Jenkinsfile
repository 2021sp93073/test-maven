pipeline{
    agent any
    stages{
        stage("Test"){
            steps{
                sh 'mvn test'
            }
        }
        stage("Build"){
            steps{
                sh 'mvn package'
            }
        }
        stage("Deploy"){
            steps{
                echo "Deploy jar to server"
            }
        }
    }
}
