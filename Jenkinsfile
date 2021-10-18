pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo '1. Clonar repositorio/pull de la branch main'
        git(url: 'https://github.com/clbaldino/jpetsotre-ing-software-utn.git', branch: 'main', credentialsId: 'clbaldino')
        sh 'git pull https://github.com/clbaldino/jpetsotre-ing-software-utn.git'
        echo '2. Compilar con gradle'
        sh 'git checkout main'
        sh '''curl -s "https://get.sdkman.io" | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"
sdk version
'''
        sh 'sdk install gradle 7.2'
        echo '3. Ejecutar el .jar'
      }
    }

  }
}