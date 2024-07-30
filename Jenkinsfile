pipeline {
    agent any
    
    tools {
        jdk 'java8'
        maven 'localMaven'
    }
    parameters {
         choice(name: 'environ', choices: ['Dev', 'pre-prod', 'prod'], description: 'Environment List')
         string(name: 'username', defaultValue: 'ranjitkumar', description: 'USer name')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    environment {
        fname = "Ranjit"
        lname = "Swain"
        version = "1.2"
        system = "Dev"
    }
    
    stages{
            stage('Build Java Application'){
                steps {
                    echo "My name is ${fname}"
                    echo "Executed from ${params.environ}"
                    echo "Executed by ${params.username} and password provided as ${params.PASSWORD}"
                }
            }
        }
}
