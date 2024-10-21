pipeline {
    agent any
    stages {
        stage('copy artifact') {
            steps {
                echo "copy artifact from other job"
                copyArtifacts filter: '**/*.war', fingerprintArtifacts: true, projectName: 'pipeline-build', selector: lastSuccessful()
            }
        }
        stage('upload to tomcat server') {
            steps {
                echo "upload build war file to tomcat server"
                deploy adapters: [tomcat9(credentialsId: 'tomcatcred', path: '', url: 'http://65.0.92.117:8090/')], contextPath: null, war: '**/*.war' 
            }
        }
    }
}
