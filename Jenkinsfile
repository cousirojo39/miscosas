pipeline {
    agent any

    parameters {
        string(name: 'LOGIN', defaultValue: '', description: 'Ingrese su login')
        string(name: 'NOMBRE', defaultValue: '', description: 'Ingrese su nombre')
        string(name: 'APELLIDO', defaultValue: '', description: 'Ingrese su apellido')
        choice(name: 'DEPARTAMENTO', choices: ['Finanzas', 'Contabilidad', 'Tecnología'], description: 'Seleccione el departamento')
    }

    stages {
        stage('Inicio') {
            steps {
                echo "Iniciando el proceso con los siguientes datos:"
                echo "Login: ${params.LOGIN}"
                echo "Nombre: ${params.NOMBRE}"
                echo "Apellido: ${params.APELLIDO}"
                echo "Departamento: ${params.DEPARTAMENTO}"
            }
        }

    }
}
