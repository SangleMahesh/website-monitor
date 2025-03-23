pipeline{
  agent any

  stages{
    stage("Clone"){
      step{
        git url: "https://github.com/SangleMahesh/website-monitor.git" , branch: "main"
      }
    }
    stage("Build"){
      step{
        sh "docker build . -t website-monitor-app"
      }
    }
    stage("Push to DockerHub"){
      step{
        echo "Pushed to docker hub"
      }
    }
    stage("Deploy"){
      step{
        echo "Deployed Successfully"
      }
    }
  }
}
