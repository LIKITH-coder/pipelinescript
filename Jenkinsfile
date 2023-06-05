pipeline {
    agent any
    stages {
        stage (git){
            steps{
                git branch: 'main', url: 'https://github.com/kampemahender122/pet_shop.git'
            }
        }
        stage(build){
            steps{
                sh 'mvn clean package'
            }
        }
        stage(deploy) {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'mahender', path: '', url: 'http://35.154.210.152:8080')], contextPath: 'pet', war: '**/*.war'
            }
        }
    }
}
