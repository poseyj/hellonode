node {
        stage "Prepare environment"
          checkout scm
          docker.image('node').inside {
            sh "node -v"
          }
}
