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
            sh "
                curl -u 2021sp93073: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 -X POST 'https://api.github.com/repos/2021sp93073/test-maven/statuses/$GIT_COMMIT' -H 'Accept: application/vnd.github.v3+json' -d '{\"state\":\"success\",\"context\":\"Continuous-Integration\",\"description\":\"Jenkins\",\"target_url\":\"http://20.255.56.92:8080/job/$JOB_NAME/$BUILD_NUMBER/console\"}'
            "
        }                
    }
}
