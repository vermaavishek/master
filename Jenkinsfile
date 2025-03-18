pipeline {
    environment{
        envVar1 = "Branch Name"
        envVar2 = "Job URL"
        envVar3 = "Build Number"
    }
    agent any 
    stages {
        stage('Build') { 
            steps {
                sh "ls -lrt >> Output.txt"
                sh 'echo ${envVar1}'
                echo "${env.BRANCH_NAME}"
            }
        }
        stage('Test') { 
            steps {
                sh 'echo ${envVar2}'
                echo "${env.JOB_URL}"
            }
        }
        stage('Deploy') { 
            steps {
                sh 'echo ${envVar3}'
                echo "${env.BUILD_NUMBER}"
            }
        }
    }
}
