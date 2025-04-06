pipeline {
    agent any

    stages {
        stage('Clonar repositorio') {
            steps {
                git branch: 'main', url: 'https://github.com/Angel-de-la-rosa/jenkins-net.git'
            }
        }

        stage('Restaurar paquetes') {
            steps {
                bat 'dotnet restore'  // Usamos bat porque es en Windows
            }
        }

        stage('Compilar') {
            steps {
                bat 'dotnet build'
            }
        }

        stage('Ejecutar tests') {
            steps {
                bat 'dotnet test'
            }
        }
    }

    post {
        success {
            echo 'Los tests se ejecutaron correctamente.'
        }
        failure {
            echo 'Hubo un error al ejecutar los tests.'
        }
    }
}
