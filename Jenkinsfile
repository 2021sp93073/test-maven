pipeline{
    agent any
    stages{
        stage("Test"){
            steps{
                echo "mvn test"
            }
        }
        stage("Build"){
            steps{
                echo "mvn clean package"
            }
        }
        stage("Deploy"){
            steps{
                sh 'cf push ./target/test-maven-1.0-SNAPSHOT.jar'
            }
        }
    }
    post{
        success{
            echo "BUILD kar"
            sh 'curl -X POST -H "Accept: application/vnd.github.v3+json" -u 2021sp93073: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 -d \'{"state":"success","context":\"Continuous-Integration","description":"Jenkins","target_url":"http://20.255.56.92:8080/job/$JOB_NAME/$BUILD_NUMBER/console"}\' https://api.github.com/repos/2021sp93073/test-maven/statuses/$GIT_COMMIT'
        }   
    }
}
