pipeline {
    agent any
    tools {nodejs "Nodejs"}
    stages {
        stage ('Instalar dependencias de Nodejs'){
            steps{
                sh "npm install"
            }
        }
        stage ('Testing de Nodejs'){
            steps{
                sh "npm test"
            }
    }
} 
