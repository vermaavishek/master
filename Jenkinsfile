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
                sh 'ls -lrt > Output.txt'
                sh 'python3 print.py > Out.txt'
                archiveArtifacts allowEmptyArchive: true, artifacts: '*.txt', fingerprint: true, followSymlinks: false, onlyIfSuccessful: true
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
