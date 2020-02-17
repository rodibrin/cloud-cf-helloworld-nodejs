@Library('piper-lib-rodibrin@PR888') _

pipeline {
    agent none
    options {
        skipDefaultCheckout()
        timestamps()
    }
    stages {
        stage('Prepare') {
            steps {
                echo "prepare instance"
                testPipelineEnvironmentSingleton script: this
                script {
                  commonPipelineEnvironment.configuration["prepare"]="DONE"
                  echo "cpe.config.[prepare] set to:" + commonPipelineEnvironment.configuration["prepare"]
                }
            }
        }
        stage('build') {
            steps {
                echo "build instance"
                script {
                  echo "cpe.config.[prepare] consumed:" + commonPipelineEnvironment.configuration["prepare"]
                }
            }
        }
    }
}                           
