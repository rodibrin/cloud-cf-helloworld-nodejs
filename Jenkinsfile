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
            }
        }
        stage('build') {
            steps {
                echo "build instance"
                testPipelineEnvironmentSingleton script: this
            }
        }
    }
}                           
