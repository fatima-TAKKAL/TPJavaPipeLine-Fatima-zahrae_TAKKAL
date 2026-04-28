pipeline {
    agent any
    tools {
        maven 'Maven'
        jdk 'JDK21'
    }
    stages {
        stage('Checkout') {
            steps {
                echo '==> Recuperation du code source...'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo '==> Compilation Maven...'
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                echo '==> Tests unitaires...'
                sh 'mvn test'
            }
            post {
                always {
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }
        stage('Package') {
            steps {
                echo '==> Creation du JAR...'
                sh 'mvn package -DskipTests'
            }
        }
        stage('Archive') {
            steps {
                echo '==> Archivage du JAR...'
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
    post {
        success {
            echo 'Pipeline termine avec SUCCES !'
        }
        failure {
            echo 'Pipeline ECHOUE - Verifier les logs'
        }
    }
}
