pipeline {
    agent any
    }
    stages {
        stage('scm') {
            steps {

                git branch: "${params.BRANCH}", url: 'https://github.com/inkgattin/game-of-life.git'
                //input message: 'Continue to next stage? ', submitter: 'qtaws,qtazure'
                
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
    
}