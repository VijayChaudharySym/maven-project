pipeline {
    agent { label 'awx_us2' }
    stages{
        stage('Build'){
            steps {
                //sh 'which mvn'
                //sh 'whoami; echo $PATH'
                //sh 'echo $PATH'
                sh '/usr/local/apache-maven/bin/mvn clean package'
            }
            post {
                success {
                    echo 'Now docking...'
                    sh "sudo docker build . -t tomcatwebapp:${env.BUILD_ID}"
                }
            }
        }
    }
}