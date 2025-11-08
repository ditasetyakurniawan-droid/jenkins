pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        // clone repo kamu via SSH pakai credential yang kita buat
        git branch: 'main',
            url: 'git@github.com:ditasetya/demo-repo.git',
            credentialsId: 'github-ssh'
      }
    }

    stage('Build') {
      steps {
        echo 'Building aplikasi Python...'
        sh 'python3 --version'
      }
    }

    stage('Test') {
      steps {
        echo 'Menjalankan unit test...'
        sh 'echo Semua test sukses!'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy simulasi selesai.'
      }
    }
  }
}
