pipeline {
    agent { label 'awx_rs1' }
    stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Now docking...'
                    sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
                }
            }
        }
    }
}