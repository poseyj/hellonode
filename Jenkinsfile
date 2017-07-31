node {
        stage "Prepare environment"
          checkout scm
          docker.image('node:boron').inside {
            stage "check version"
                sh "node -v"
                  
            stage "install"
                sh "npm install"
          }
}
