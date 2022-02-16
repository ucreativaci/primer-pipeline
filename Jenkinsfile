pipeline {
    agent any

    stages {
        stage('Compilacion del codigo') {
            steps {
                sh "dotnet"
            }
        }
        
        stage('Ejecutar pruebas de vulnerabilidad') {
            steps {
                echo "Hello World1"
            }
        }
        
        stage('Desplegar en AWS') {
            steps {
                echo "Desplegando codigo en AWS..."
            }
        }
    }
}
