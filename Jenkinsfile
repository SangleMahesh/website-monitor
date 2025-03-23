pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "sanglemahesh/website-monitor-app"
    }

    stages {
        stage("Clone") {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/SangleMahesh/website-monitor.git'
            }
        }

        stage("Build") {
            steps {
                sh "docker build -t ${DOCKER_IMAGE} ."
            }
        }

        stage("Push to DockerHub") {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', 
                                                 usernameVariable: 'DOCKER_USER', 
                                                 passwordVariable: 'DOCKER_PASS')]) {
                    sh "echo $DOCKER_PASS | docker login -u $DOCKER_USER -p $DOCKER_PASS"
                    sh "docker push ${DOCKER_IMAGE}"
                }
            }
        }

        stage("Deploy") {
            steps {
                echo "Deployed Successfully"
            }
        }
    }
}
