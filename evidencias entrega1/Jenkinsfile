pipeline {
    agent any

    stages {
        stage('1. Descargar Repositorio') {
            steps {
                echo 'Clonando el repositorio desde GitHub..'
                checkout scm
            }
        }

        stage('2. Validar Sintaxis YAML') {
            steps {
                echo 'Validando que el archivo docker-compose.yml sea correcto...'
                // Este comando verifica la sintaxis del archivo sin levantar nada
                sh 'docker compose config'
            }
        }

        stage('3. Desplegar Infraestructura') {
            steps {
                echo 'Levantando los contenedores de Ubuntu y la red...'
                // Levanta los servicios en segundo plano (-d)
                sh 'docker compose up -d'
            }
        }

        stage('4. Verificar Estado') {
            steps {
                echo 'Validando que los contenedores estén corriendo...'
                sh 'docker compose ps'
            }
        }
    }
}