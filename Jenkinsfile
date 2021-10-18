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
        sh './gradlew build'
        echo '3. Ejecutar el .jar'
        sh 'SERVER_PORT=8888 ./gradlew bootRun'
      }
    }

    stage('Test') {
      steps {
        sh './gradlew test'
      }
    }

    stage('Validate') {
      steps {
        echo 'Stage de validación'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Stage de Deploy'
      }
    }

  }
}