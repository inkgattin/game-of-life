pipeline {
    agent any
    triggers {
        cron('* * * * *')
        pollSCM('* * * * *')
    }
    parameters {
        string(name: 'BRANCH', defaultValue: 'master', description: 'Branch to build' )
    }
    stages {
        stage('scm') {
            steps {

                git branch: "${params.BRANCH}", url: 'https://github.com/asquarezone/game-of-life.git'
                //input message: 'Continue to next stage? ', submitter: 'qtaws,qtazure'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
    post {
        success {
            archive '**/gameoflife.war'
            
        }
        
    }
}