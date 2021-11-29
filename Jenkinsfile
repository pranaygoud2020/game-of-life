pipeline {
    agent { label 'GOL' }
    stages{
        stage( 'scm'){
            steps {
                git branch: 'master', url:'https://github.com/pranaygoud2020/game-of-life.git'
            }
        }
        stage ( 'build') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            artifacts '**/*.war'
            junit '**/TEST-*.xml'
        }
            }
}