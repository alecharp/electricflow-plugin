pipeline {
  agent none
  stages {
    stage('Test Plugin on Linux') {
      agent {
        docker { image 'ecdocker/eflow-ce' }
        label 'linux'
      }
      steps {
        buildPlugin(configurations: [ platform: "linux", jdk: "8", jenkins: null ])
      }
    }
 }
 stages {
   stage('Test default configurations'){
    buildPlugin(configurations: buildPlugin.recommendedConfigurations())
   }
 }
}