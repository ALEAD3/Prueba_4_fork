pipeline {
    agent any

    stages {

        stage('Clonar Código') {
            steps {
                checkout scm
            }
        }

        stage('Ejecutar Pruebas Python') {
            steps {
                sh '''
                    echo "===== ARCHIVOS EN JENKINS ====="
                    pwd
                    ls -la

                    echo "===== PRUEBAS PYTHON ====="

                    docker run --rm \
                        -v jenkins_home:/jenkins_home \
                        -w /jenkins_home/workspace/prueba4 \
                        python:3.11-slim \
                        python -m unittest test_app.py
                '''
            }
        }
    }
}
