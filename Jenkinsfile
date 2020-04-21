pipeline {
  agent none
  stages {
    stage('Run integration tests') {
      steps {
        node {
              docker.image('ecdocker/eflow-ce-server').withRun('-p8443:8443') { c ->
                sh 'ectool --server 127.0.0.1 --timeout 10000 login admin changeme'
              }
            }
        buildPlugin(configurations: [ 'platform': "linux", 'jdk': "8", 'jenkins': null ])
      }
    }

    stage('Test recommended configurations'){
      steps {
        buildPlugin(configurations: buildPlugin.recommendedConfigurations())
      }
    }

  }
}