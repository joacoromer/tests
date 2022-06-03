pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                sh 'echo "Acá se hace un checkout del repo"'
                sh '''
                    echo "Y acá mostraría todos los archivos"
                    ls -l
                '''
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
