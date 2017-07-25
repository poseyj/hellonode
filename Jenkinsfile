podTemplate(label: 'mypod', containers: [
  containerTemplate(name: 'debian', image: 'debian', ttyEnabled: true, command: 'cat'),
  containerTemplate(name: 'ubuntu', image: 'ubuntu', ttyEnabled: true, command: 'cat')
]) {
  node('mypod') {
    container('debian') {
      stage('stage 1') {
        sh 'echo hello'
        sh 'sleep 5'
        sh 'echo world'
      }

      stage('stage 2') {
        sh 'echo hello'
        sh 'sleep 5'
        sh 'echo world'
      }
    }
  }
}
