pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    tools {
        maven 'M3'
    }
    stages {
        stage("Compile") {
            steps {
                sh "mvn compile"
            }
        }
        stage("Unit test") {
            steps {
                sh "mvn clean test"
            }
        }
        stage ("Package") {
            steps {
                sh "mvn build"
            }
        }
        stage ("Probar si funciona Docker") {
            steps {
                sh "docker version"
            }
        }
    }
}