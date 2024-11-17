pipeline {
    agent any
    stages {
        stage('download code from git') {
            steps {
                echo "this will download code from git"
                git branch: 'main', url: 'https://github.com/jpgandhi/maven-jenkins4.git'
            }
        }
        stage('run the dockerfile') {
            steps {
                echo "this will run the dockerfile and build the war file"
                sh 'docker build -t sample:v1 .'
            }
        }        
    }
}
