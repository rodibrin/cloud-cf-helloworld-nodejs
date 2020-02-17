@Library('piper-lib-rodibrin@PR888') _

node() {
  stage('prepare') {
    echo "prepare instance"
    checkout([$class: 'GitSCM', branches: [[name: '*/1-ppiper-cx']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/rodibrin/cloud-cf-helloworld-nodejs']]])

    testPipelineEnvironmentSingleton script: this
    testPipelineEnvironmentSingleton.getCPE().setValue("prepare_1","done")
    testPipelineEnvironmentSingleton.getCPE().getValueMap()["prepare_2"]="done"
  }
  stage('build') {
      input message: "build"
      testPipelineEnvironmentSingleton script: this
  }
}                           
