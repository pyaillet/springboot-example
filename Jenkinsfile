pipeline {
    agent any

    stages {
        def app;
        stage('Build') {
            steps {
                echo 'Building..'
                ./mvnw package -DskipTests

                app = docker.build "app"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                docker run app
            }
        }
    }
}