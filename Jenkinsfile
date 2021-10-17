pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'git checkout main'
        sh 'git pull git@github.com:clbaldino/jpetsotre-ing-software-utn.git'
        sh 'cd jpetsotre-ing-software-utn'
        sh 'gradle build'
        sleep 5
        sh './gradlew bootRun'
      }
    }

    stage('Test') {
      steps {
        sh '''cd jpetsotre-ing-software-utn
./gradlew test'''
      }
    }

    stage('Validate') {
      steps {
        echo 'This step should validate'
      }
    }

    stage('Deploy') {
      steps {
        echo 'This test should deploy'
      }
    }

  }
}