pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        sh 'git checkout -b mergetest'
      }
    }

    stage('list') {
      steps {
        sh 'git branch -a'
      }
    }

    stage('new branches') {
      parallel {
        stage('new branches') {
          steps {
            sh 'git branch test1'
          }
        }

        stage('again') {
          steps {
            sh 'git branch test2'
          }
        }

        stage('once again') {
          steps {
            sh 'git branch test3'
          }
        }

      }
    }

    stage('list check') {
      steps {
        sh 'git branch -a'
      }
    }

    stage('merge') {
      steps {
        sh 'git merge test1 test2'
      }
    }

    stage('rebase') {
      steps {
        sh 'git rebase test1 test3'
      }
    }

    stage('destroy') {
      steps {
        sh 'git branch -d test1'
      }
    }

    stage('notif') {
      steps {
        echo 'Sir,Work Done Sir'
      }
    }

  }
}