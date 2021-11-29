pipeline {
    agent { label 'GOL' }
     triggers {
        cron('H * * * *')
        pollSCM('* * * * *')
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
            archive '**/gameoflife.war'
            junit '**/TEST-*.xml'
        }
            }
}