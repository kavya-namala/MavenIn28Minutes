pipeline {
  agent any
  stages {
    stage('Pre-Build') {
      parallel {
        stage('Pre-Build') {
          steps {
            sh '''export M2_HOME=/OPT/homebrew/cellar/maven/3.8.6/libexec # your Maven home path
export PATH=$PATH:$M2_HOME/BIN


'''
          }
        }

        stage('Files') {
          steps {
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('buld') {
      steps {
        sh '''export M2_HOME=/OPT/homebrew/cellar/maven/3.8.6/libexec # your Maven home path
export PATH=$PATH:$M2_HOME/BIN

'''
      }
    }

    stage('Test') {
      steps {
        junit(testResults: '**/surefire-reports/**/*.xml', allowEmptyResults: true)
      }
    }

    stage('Artifact') {
      steps {
        archiveArtifacts(artifacts: 'MavenIn28Minutes/target/.jar', allowEmptyArchive: true, caseSensitive: true)
      }
    }

  }
}