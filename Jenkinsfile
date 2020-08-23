pipeline {
  agent {
    node {
      label 'java'
    }

  }
  stages {
    stage('maven ') {
      parallel {
        stage('git ') {
          steps {
            git(url: 'https://github.com/asquarezone/game-of-life.git', branch: 'master', credentialsId: 'git', poll: true)
          }
        }

        stage('maven') {
          steps {
            bat 'mvn clean '
          }
        }

      }
    }

  }
  environment {
    java = '11'
  }
}