pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('git') {
      steps {
        dir(path: '/home/shiyanlou/test_git') {
          git(url: 'git@github.com:qimanchen/test_git.git', branch: 'master', credentialsId: '1630389e-8146-4245-bbdc-33ec07e258f3')
        }

      }
    }
    stage('build') {
      steps {
        sh 'sudo -H pip install -r requirements.txt'
      }
    }
    stage('run') {
      steps {
        sh 'python app.py'
      }
    }
  }
}