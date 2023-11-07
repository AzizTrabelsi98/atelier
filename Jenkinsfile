pipeline {
    agent any

    stages {

              stage('Getting project from Git') {
            steps{
      			checkout([$class: 'GitSCM', branches: [[name: '*/main']],
			extensions: [],
			userRemoteConfigs: [[url: 'https://github.com/AzizTrabelsi98/atelier.git']]])
            }
        }
      
        stage('close containers') {
            steps {
                sh 'docker stop mysqldbco Mohamedaziztrabelsi-5Twin5-G6'
                sh 'docker rm mysqldbco Mohamedaziztrabelsi-5Twin5-G6'
                sh 'docker compose up -d'
            }
        }
      
        stage('start app') {
            steps {
                sh 'docker compose up -d'
            }
        }
      
    }
}
