pipeline {
    agent any
    tools {nodejs "node"}
    stages {
        stage ('Instalar dependencias para Nodejs'){
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
}
