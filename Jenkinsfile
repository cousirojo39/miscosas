pipeline {
    agent any
    tools {nodejs "Nodejs 21.7.3"}
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
