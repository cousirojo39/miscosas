pipeline {
    agent any
    parameters {
        string(name: 'NOMBRE', defaultValue: '', description: 'Ingrese el nombre del usuario')
        string(name: 'APELLIDO', defaultValue: '', description: 'Ingrese el apellido del usuario')
        choice(name: 'DEPARTAMENTO', choices: ['Finanzas', 'Contabilidad', 'Tecnología'], description: 'Seleccione el departamento')
    }
    stages {
        stage('Generar Contraseña Temporal') {
            steps {
                script {
                    // Generar una contraseña temporal. Puedes personalizar la lógica según tus necesidades.
                    def tempPassword = UUID.randomUUID().toString().substring(0, 8)
                    echo "Contraseña temporal generada: ${tempPassword}"
                    // Aquí puedes agregar el código para crear el usuario con la contraseña temporal
                    // Por ejemplo, si estás interactuando con una base de datos o un sistema externo, puedes hacerlo aquí.
                }
            }
        }
    }
}
              

