#!groovy
//  groovy Jenkinsfile
properties([disableConcurrentBuilds()])\

pipeline  {
        agent { 
           label ''
        }

    options {
        buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
        timestamps()
    }
    stages {
        stage("Git clone") {
            steps {
                sh '''
                cd /home/ubuntu/
                git clone https://github.com/Vlad1ck228/test           
                '''
            }
        }    
        stage("Work") {
            steps {
                sh '''
                cd /home/ubuntu/zabbix
                docker-compose up -d
                '''
            }
        }   
    }
}
