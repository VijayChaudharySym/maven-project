pipeline {
    agent { label 'awx_us2' }
    stages{
        stage('Build'){
            steps {
                //sh 'which mvn'
                sh 'whoami; echo $PATH'
                sh 'echo $PATH'
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