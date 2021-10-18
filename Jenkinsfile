pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'a. Clonar repositorio/pull de la branch main'
        git(url: 'https://github.com/clbaldino/jpetsotre-ing-software-utn.git', branch: 'main', credentialsId: 'clbaldino')
        sh 'git pull https://github.com/clbaldino/jpetsotre-ing-software-utn.git'
        sh 'git checkout main'
        echo 'b. Compilar con gradle'
        catchError() {
          sh './gradlew build'
        }

        echo '3. Ejecutar el .jar'
        sh '''export BUILD_ID=dontKillMe
export SERVER_PORT=8888
nohup ./gradlew bootRun &'''
        sleep 20
        sh 'tail nohup.out'
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