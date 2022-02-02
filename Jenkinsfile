pipeline {
    agent {label "Slave-1"}

    stages {
        stage('Build') {
            steps {
                bat "docker build -t naveends/myfirstpipeline G:\\JENKINS\\SLAVES\\SLAVE-1\\workspace\\MyJenkinsProject"
            }
        }
        stage('Clean') {
            steps {
                 bat "docker rm --f mypipelineweb || true"
            }
        }
        stage('Deploy') {
            steps {
                bat "docker run -it -d -p 96:80 --name mypipelineweb naveends/myfirstpipeline"
            }
        }
    }
}