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
                curl \
                  -X POST \
                  -H "Accept: application/vnd.github.v3+json" \
                  https://api.github.com/repos/2021sp93073/test-maven/statuses/$GIT_COMMIT \
                  -d '{"state":"success","target_url":"http://20.255.56.92:8080/job/$JOB_NAME/$BUILD_NUMBER/console","description":"Jenkins","context":"Continuous-Integration"}'
               """
        }                
    }
}
