pipeline {
    agent any
    tools {
        maven 'Maven'
        jdk 'JDK'
    }
    stages {
        stage('Clonar código') {
            steps {
                git url: 'https://github.com/JABELTR/java-jenkins-ci-example.git', branch: 'main'
            }
        }
        stage('Compilar') {
            steps {
                sh 'mvn clean compile'
            }
        }
stage('Pruebas') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Empaquetar') {
            steps {
                sh 'mvn package'
            }
        }
    }
    post {
        success {
            echo 'La compilación y las pruebas fueron exitosas.'
        }
        failure {
            echo 'Hubo errores en la compilación o en las pruebas.'
        }
    }
}