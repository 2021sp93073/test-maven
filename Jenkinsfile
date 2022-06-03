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
            echo "BUILD BARABAR"
            script{
                sh "curl -u 2021sp93073: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 -X POST 'https://api.github.com/repos/2021sp93073/test-maven/statuses/$GIT_COMMIT' -H 'Accept: application/vnd.github.v3+json' -d '{\"state\":\"success\",\"context\":\"Continuous-Integration\",\"description\":\"Jenkins\",\"target_url\":\"http://20.255.56.92:8080/job/$JOB_NAME/$BUILD_NUMBER/console\"}'"
            }
        }   
    }
}
