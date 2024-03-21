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

              

