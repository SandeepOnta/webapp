pipeline {
  agent {
    node {
      label 'Linux'
    }
    
  }
  stages {
    stage('scm-checkout') {
      steps {
        git(url: 'https://github.com/deepakbhattarai/webapp.git', branch: 'master')
      }
    }
    stage('build') {
      steps {
        sh 'mvn -f CounterWebApp/pom.xml clean install'
      }
    }
    stage('archive') {
      steps {
        archiveArtifacts(artifacts: '**/target/*.war', onlyIfSuccessful: true)
      }
    }
    stage('deploy') {
      steps {
        echo 'This is a files in files'
      }
    }
  }
}