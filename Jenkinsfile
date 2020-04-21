pipeline {
  agent none
  stages {
    stage('Test Plugin on Linux') {
      agent {
        docker {
          label 'linux'
          image 'ecdocker/eflow-ce'
        }
      }
      steps {
        buildPlugin(configurations: [ platform: "linux", jdk: "8", jenkins: null ])
      }
    }
 }
 stages {
   stage('Test default configurations'){
     steps {
       buildPlugin(configurations: buildPlugin.recommendedConfigurations())
     }
   }
 }
}