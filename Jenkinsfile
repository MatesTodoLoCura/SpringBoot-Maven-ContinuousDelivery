pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    tools {
        maven 'mvn'
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
                sh "mvn package"
            }
        }
        stage ("Probar si funciona Docker") {
            steps {
                sh "docker version"
            }
        }
    }
}