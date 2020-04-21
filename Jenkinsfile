pipeline {
  agent {
    docker { image 'ecdocker/eflow-ce' }
 }
 stages {
   stage('Test Plugin') {
     steps {
       buildPlugin(configurations: buildPlugin.recommendedConfigurations())
     }
   }
 }
}