pipeline {
    agent any
    
    tools {
        maven 'localMaven'
    }
    stages{
            stage('Build Java Application'){
                steps {
                    sh 'mvn clean package'
                }
                post {
                    success {
                        echo 'Archiving the artifacts'
                        archiveArtifacts artifacts: '**/target/*.war'
                    }
                }
            }
            stage('Deployment to Staging server'){
                parallel{
                    stage('Deploy to Tomcat Server1'){
                        steps{
                            deploy adapters: [tomcat9(credentialsId: 'tomcatcred', path: '', url: 'http://13.126.199.225:8080/')], contextPath: null, war: '**/*.war'
                        }
                    }
                    stage('Deploy to Tomcat Server2'){
                        steps{
                            echo "Deploying to Tomcat Server 2"
                        }
                    }
                }

            }
        }
}
