pipeline {
    agent any
    stages {
        stage('scm') {
            steps {

                git 'https://github.com/inkgattin/game-of-life.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}