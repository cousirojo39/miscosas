pipeline {
    agent any
    // 1. Datos de entrada 
    parameters {
        string(name: 'Login', description: 'Ingrese Nombre de Usuario', defaultValue: '')
        string(name: 'NombreApellido', description: 'Ingrese su Nombre y Apellido', defaultValue: '')
        choice(name: 'Departamento', choices: ['Contabilidad', 'Finanzas', 'Tecnología'], description: 'Escoja Departamento al que pertenece')
    }

    stages {
        // 2. Generar un password temporal
        stage('Generar password temporal') {
            steps {
                script {
                    def passwordTemporal = sh 'openssl rand -base64 10'
                    echo "Su contraseña es: ${passwordTemporal}"
                    // 3. Persiste el password temporal para ser usado por el Operador y poder enviarlo por correo.
                    env.PASSWORD_TEMPORAL = passwordTemporal
                }
            }
        }
        // 1. Crear usuario
        stage('Crear usuario') {
            steps {
                script {
                    sh "useradd -m -s /bin/bash -c '${params.NombreApellido}' -G ${params.Departamento} ${params.Login}"
                    sh "echo ${params.Login}:${passwordTemporal} | chpasswd"
                }
            }
        }
    }
}
