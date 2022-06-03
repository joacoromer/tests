pipeline {
    agent any

    parameters{
        choice(name: "SCRIPT", choices: ['cy:run','cy:acciones','cy:compras'], description: "Elija el script a ejecutar")
    }
    stages {
        stage('Building app') {
            steps {
                echo 'Acá se buildea la app'
            }
        }
        stage('Test') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Reports') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
