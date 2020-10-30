pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'cd applications/microservice'
                sh 'docker build . -t python-microservice'
            }
        }

        stage ('Unit Test') {
            steps {
                sh 'docker run python-microservice pytest -v'
            }
        }
    }
}
