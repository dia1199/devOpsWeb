pipeline {
    agent any
    
    tools {
        jdk 'java8'
        maven 'localMaven'
    }
    parameters {
         string(name: 'environ', defaultValue: ['Dev', 'pre-prod', 'prod'], description: 'Environment List')
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
                    echo "Executed from ${environ}"
                }
            }
        }
}
