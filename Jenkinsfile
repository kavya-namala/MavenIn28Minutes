pipeline {
  agent any
  stages {
    stage('Pre-Build') {
      steps {
        sh '''export M2_HOME=/OPT/homebrew/cellar/maven/3.8.6/libexec # your Maven home path
export PATH=$PATH:$M2_HOME/BIN


'''
      }
    }

  }
}