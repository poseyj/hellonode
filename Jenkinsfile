node {
        stage "Prepare environment"
          checkout scm
          docker.image('node:boron').inside {
            sh "node -v"
          }
}
