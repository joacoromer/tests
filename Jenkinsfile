pipeline {
    agent any

    parameters{
        string(name: "SPEC", defaultValue: "cypress/integration/1-getting-started/todo.spec.js", description: "Por defecto se ejecutará el todo.spec.js del getting-started")
        choice(name: "SCRIPT", choices: ['cy:run','cy:acciones','cy:compras'], description: "Elija el script a ejecutar")
        choice(name: "BROWSER", choices: ['chrome'], description: "Navegador a usar")
    }
    stages {
        stage('Building app') {
            steps {
                echo 'Acá se buildea la app'
            }
        }
        stage('Test') {
            steps {
                sh '/usr/bin/npm install'
                sh 'npx cypress run --spec ${SPEC}'
            }
        }
        stage('Reports') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
