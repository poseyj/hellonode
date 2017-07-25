/**
 * This pipeline describes a multi container job, running Maven and Golang builds
 */

podTemplate(label: 'pipeline', 
  containers: [
    containerTemplate(name: 'nodejs', image: 'node:boron', ttyEnabled: true, command: 'cat'),
    containerTemplate(name: 'docker', image: 'docker:1.12.6',       command: 'cat', ttyEnabled: true)
  ],
  volumes: [hostPathVolume(hostPath: '/var/run/docker.sock', mountPath: '/var/run/docker.sock')]
  ) {

  node('pipeline') {

    stage('Checkout') {
      checkout scm
    }
    
    stage('Build') {
      container('nodejs') {
        stage('Version') {
          sh """
          node -v
          ls -als
          """
        }
        stage('Install') {
          sh """
          npm install
          ls -als
          """
        }
      }
    }
    stage('Docker') {
      container('docker') {
        sh """
        docker -v
        ls -als
        """
      }
    }
    
  }
}
