pipeline {
    agent any
    tools {
        maven 'maven3'
        jdk 'java17'
    }
    stages {
        stage('download code from git') {
            steps {
                echo "this will download code from git"
                git branch: 'main', url: 'https://github.com/jpgandhi/maven-jenkins4.git'
            }
        }
        stage('make build using maven') {
            steps {
                echo "build java project using maven"
                sh 'mvn clean package'
            }
        }
        stage('archive the build file') {
            steps {
                echo "archive the build war file"
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }
        stage('start build other project') {
            steps {
                echo "trigger the other project job"
                build wait: false, job: 'pipeline-deploy'
            }
        }
    }
}
