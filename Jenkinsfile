@Library ('myLibrary')_
pipeline {
    agent any
    
    tools {
        maven 'localMaven'
    }

stages{
        stage('Build'){
            steps {
                script{
                    build_demo()
                }
            }
            post {
                success {
                    echo 'Archiving the artifacts'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

        stage ('Deployments'){
            parallel{
                stage ("Deploy to Staging"){
                    steps {
                        echo "Deploy to Staging"
                    }
                }
            }
        }
    }
}
