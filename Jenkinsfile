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
          stage('SONAR ANALYSIS') {
            steps{
                withSonarQubeEnv('SONAR-8.9LTS') {
                // requires SonarQube Scanner for Maven 3.2+
                sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
                 
                }
            }
        }
    }
}