pipeline {
    agent any
    parameters {
        string(name: 'name', defaultValue: '', description: 'Ingresa un nombre')
        string(name: 'age', defaultValue: '', description: 'Ingresa tu edad')
    }
    stages {
        stage('Input') {
            steps {
                script {
                    // Los parametros pueden ser accedidos mediante params.parameterName
                    echo "Hola, ${params.name}! Tienes ${params.age} de edad."
                }
            }
        }
    }
}