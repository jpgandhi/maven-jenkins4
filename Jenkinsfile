pipeline {
    agent any
    stages {
        stage('download code from git') {
            steps {
                echo "this will download code from git"
                git branch: 'main', url: 'https://github.com/jpgandhi/maven-jenkins4.git'
            }
        }
    }
}
