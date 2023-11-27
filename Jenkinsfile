pipeline {
    agent {
        docker { image 'public.ecr.aws/docker/library/maven:3.9-sapmachine' }
    }
    stages {
        stage('Source') {
            steps {
                echo "Source"
            }
        }
        stage('Clean') {
            steps {
                echo "clean"
            }
        }
        stage('Test') {
            steps {
                echo "test"
            }
        }
        stage('Package') {
            steps {
                echo "package"
            }
        }
    }
}