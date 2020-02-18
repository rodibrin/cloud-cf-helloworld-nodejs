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
                prepareDefaultValues script: this
                script {
//                    import com.sap.piper.DefaultValueCache
                    def defaultValues = prepareDefaultValues.defaultValueCache.getDefaultValues()
                    defaultValues.each { echo "[prepare] dv.$it = $it" }
                }
            }
        }
        stage('build') {
            steps {
                echo "build instance"
                script {
                    def defaultValues = prepareDefaultValues.defaultValueCache.getDefaultValues()
                    defaultValues.each { echo "[build] dv.$it = $it" }
                }
            }
        }
    }
}
