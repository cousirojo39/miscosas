pipeline {
    agent any

    stages {
        stage('Solicitar Información') {
            steps {
                script {
                    def userInput = input(
                        id: 'userInput', 
                        message: 'Por favor, rellene la siguiente información:', 
                        parameters: [
                            string(name: 'LOGIN', defaultValue: '', description: 'Ingrese su login'),
                            string(name: 'NOMBRE', defaultValue: '', description: 'Ingrese su nombre'),
                            string(name: 'APELLIDO', defaultValue: '', description: 'Ingrese su apellido'),
                            choice(name: 'DEPARTAMENTO', choices: ['Finanzas', 'Contabilidad', 'Tecnología'], description: 'Seleccione el departamento')
                        ]
                    )
                    
                    echo "Login: ${userInput['LOGIN']}"
                    echo "Nombre: ${userInput['NOMBRE']}"
                    echo "Apellido: ${userInput['APELLIDO']}"
                    echo "Departamento: ${userInput['DEPARTAMENTO']}"
                }
            }
        }

        // Aquí puedes agregar más etapas según sea necesario
    }
}
