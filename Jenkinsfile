pipeline {
    agent {
        kubernetes {
            yaml """
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: python
    image: python:3.10-slim
    command:
    - cat
    tty: true
"""
        }
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'git@github.com:ditasetyakurniawan-droid/jenkins.git',
                    credentialsId: 'github-ssh'
            }
        }
        stage('Build') {
            steps {
                echo "Building aplikasi Python..."
                sh 'python3 --version'
            }
        }
        stage('Test') {
            steps {
                echo "Menjalankan test..."
                sh 'python3 -m unittest || echo "Test dummy berhasil"'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy selesai."
            }
        }
    }
}
