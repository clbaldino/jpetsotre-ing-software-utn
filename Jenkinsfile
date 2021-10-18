pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/clbaldino/jpetsotre-ing-software-utn.git', branch: 'main', credentialsId: 'clbaldino')
        sh 'git clone https://github.com/clbaldino/jpetsotre-ing-software-utn.git'
      }
    }

  }
}