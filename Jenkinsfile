pipeline {
    agent any

    environment {
        DOCKER_HOST = 'tcp://localhost:2375'
    }

    stages {
        stage('1. Descargar Repositorio') {
            steps {
                echo 'Clonando el repositorio desde GitHub...'
                checkout scm
            }
        }

        stage('2. Validar Sintaxis YAML') {
            steps {
                echo 'Validando que el archivo docker-compose.yml sea correcto...'
                // Cambiamos 'sh' por 'bat' para que funcione en Windows
                bat 'docker compose config'
            }
        }

        stage('3. Desplegar Infraestructura') {
            steps {
                echo 'Levantando los contenedores de Ubuntu y la red...'
                // Cambiamos 'sh' por 'bat'
                bat 'docker compose up -d'
            }
        }

        stage('4. Verificar Estado') {
            steps {
                echo 'Validando que los contenedores estén corriendo...'
                // Cambiamos 'sh' por 'bat'
                bat 'docker compose ps'
            }
        }
    }
}