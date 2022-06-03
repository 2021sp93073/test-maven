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
             echo "BUILD last"
            sh """
                curl -i -H "Authorization: token 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" -X POST -H "Accept: application/vnd.github.v3+json" -d '{\"state\":\"success\",\"context\":\"Continuous-Integration\",\"description\":\"Jenkins\",\"target_url\":\"http://20.255.56.92:8080/job/$JOB_NAME/$BUILD_NUMBER/console\"}' http://api.github.com/repos/2021sp93073/test-maven/statuses/$GIT_COMMIT
            """
        }                
    }
}
