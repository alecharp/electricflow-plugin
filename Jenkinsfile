pipeline {
  agent none
  stages {
    stage('Test Plugin on Linux') {
      agent {
        label 'linux'
        docker { image 'ecdocker/eflow-ce' }
      }
      steps {
        buildPlugin(configurations: [ platform: "linux", jdk: "8", jenkins: null ])
      }
    }
 }
 buildPlugin(configurations: buildPlugin.recommendedConfigurations())
}