pipeline {
  agent any
  stages {
    stage('git') {
      steps {
        git(url: 'https://github.com/kevingu-01/maven-samples-A6.git', branch: 'master')
      }
    }

    stage('bisect setup') {
      steps {
        sh 'git bisect start 198644632661c67b6c32f59e9047c11a70685e15 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5'
      }
    }

    stage('bisect run') {
      steps {
        sh 'git bisect run mvn clean test'
      }
    }

    stage('bisect reset') {
      steps {
        sh 'git bisect reset'
      }
    }

  }
}