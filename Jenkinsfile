pipeline {
    agent any

    stages {
        stage('code fetch') {
            steps {
                echo 'code fetch from github'
                git url:'https://github.com/mystified7545/ZenkinsDemo.git',branch: 'main'
            }
        }
        stage('build') {
            steps {
                echo 'code build with docker'
                sh 'docker build -t my-jenkins-site .'
            }
        }
        stage('deploy') {
            steps {
                echo 'Deploy on container'
                sh 'docker run -d -p 80:80 my-jenkins-site'
            }
        }
        
    }
}
