pipeline {
    agent any
    tools {
        maven 'Maven'
        jdk 'JDK-23'
        git 'Git'
    }
    stages {
        stage('Clonar código') {
            steps {
                git url: 'https://github.com/JABELTR/java-jenkins-ci-example.git', branch: 'main'
            }
        }
        stage('Compilar') {
            steps {
                bat 'mvn clean compile'
            }
        }
stage('Pruebas') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Empaquetar') {
            steps {
                bat 'mvn package'
            }
        }
    }
    post {
        success {
            echo 'La compilacion y las pruebas fueron exitosas.'
        }
        failure {
            echo 'Hubo errores en la compilacion o en las pruebas.'
        }
    }
}