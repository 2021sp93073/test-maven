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
            sh """
                set -x
                curl \"https://api.github.com/repos/2021sp93073/test-maven/statuses/$GIT_COMMIT\" \
                    -H \"Content-Type: application/json\" \
                    -X POST \
                    -d \"{\\\"description\\\": \\\"Jenkins\\\", \\\"state\\\": \\\"success\\\", \\\"context\\\": \\\"CI\\\", \\\"target_url\\\": \\\"http://20.255.56.92:8080/job/$JOB_NAME/$BUILD_NUMBER/console\\\"}\"
                """
        }                
    }
}
