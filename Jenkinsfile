pipeline {
    agent any
    stages{
        stage(git){
            steps {
                git branch: 'main', url: 'https://github.com/LIKITH-coder/live01.git'
            }
        }
        stage (build){
            steps {
                sh 'mvn clean package'
            }
        }
        stage(deploy){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'lavanya', path: '', url: 'http://3.6.39.194:4444/')], contextPath: 'live', war: '**/*.war'
            }
        }
    }
}
