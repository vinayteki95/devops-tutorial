pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'cd applications/microservice; docker build . -t python-microservice'
            }
        }

        stage ('Unit Test') {
            steps {
                sh 'docker run python-microservice pytest -v'
            }
        }

        stage ('Push Build') {
            steps {
                sh 'docker tag python-microservice 1k3tv1nay/python-microservice;\
                    docker push 1k3tv1nay/python-microservice'
            }
        }
    }
}
