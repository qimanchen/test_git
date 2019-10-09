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
          git(url: 'https://github.com/qimanchen/test_git.git', branch: 'master', credentialsId: '2956b9f3-7c19-44d5-8b5e-ad8fba423e05')
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