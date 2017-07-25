/**
 * This pipeline describes a multi container job, running Maven and Golang builds
 */

podTemplate(label: 'node1', containers: [
  containerTemplate(name: 'nodejs', image: 'node:boron', ttyEnabled: true, command: 'cat')
  ]) {

  node('node1') {
    stage('Build a NodeJS project') {
      container('nodejs') {
        stage('Checkout') {
          checkout scm
        }
        stage('Version') {
          sh """
          node -v
          ls -als
          """
        }
      }
    }

  }
}
