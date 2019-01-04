node ('schiavo') {
    stage('Checkout') {
        checkout scm
    }

    if (env.BRANCH_NAME == 'jenkinsfile') {
        stage("Compile Production Configurator") {
            withEnv(["JAVA_HOME=/opt/jdk"]) {
                withMaven(maven: 'maven-3.6') {
                    sh "export PATH=$MVN_CMD_DIR:$PATH && mvn clean install"
                }
            }
        }
    }
}
