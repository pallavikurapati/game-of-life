pipeline {
    agent{label 'JDK11'}
    Stages { 
    stage('source code') {
        steps {
    git url:'https://github.com/wakaleo/game-of-life.git'
    branch : 'master'
        }
    }
    stage ('build the code') {
        steps {
            sh-script :'mvn compile'
        }
    }
    stage ('reporting') {
        steps {
            Junit test Results : '**/surefire-report/*.xml'
        }
    }
    stage ('test results') {
        steps {
            archiveArtifacts artifacts: '**/*.war', followSymlinks: false
        }
    }
 }
        
