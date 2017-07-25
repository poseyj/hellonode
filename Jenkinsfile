/**
 * This pipeline describes a multi container job, running Maven and Golang builds
 */

podTemplate(label: 'maven-golang', containers: [
  containerTemplate(name: 'nodejs', image: 'node:boron', ttyEnabled: true, command: 'cat')
  ]) {

  node('maven-golang') {
    stage('Build a NodeJS project') {
      git url: 'https://github.com/hashicorp/terraform.git'
      container('nodejs') {
        sh """
        node -v
        """
      }
    }

  }
}
