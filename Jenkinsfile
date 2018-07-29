pipeline {
    agent any
    tools {
        maven 'localMaven'
        java 'localJDK'
    }
    stages{
        stage('Build'){
            steps {
                echo 'Now Build...'
                sh 'mvn clean package'
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
