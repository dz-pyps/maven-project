pipeline {
    agent any

    tools {
        maven 'localMaven'
    }

    stages{
        stage('Build'){
            steps {
                sh 'mvn clean install -U'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}