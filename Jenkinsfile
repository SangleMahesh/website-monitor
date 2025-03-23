pipeline {
    agent any

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
               withCredentials([usernamePassword(credentialsId:"docker-hub-credentials",passwordVariable:"dockerHubPass",usernameVariable:"dockerHubUser")]){
                sh "docker tag website-monitor-app-new ${env.dockerHubUser}/website-monitor-app-new:latest"
                sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                 sh "docker push ${env.dockerHubUser}/website-monitor-app:latest"
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
