pipeline{
    agent any
    stages{
        stage("Git clone"){
            steps{
                git branch: '${HEAD}', url: 'https://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@github.com/2021sp93073/test-maven.git'
            }
        }
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
}
