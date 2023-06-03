pipeline{
    agent{
        label 'linux'
    }
    stages{
        stage('checkout git'){
            steps{
                dir('vector-role'){
                    git branch: 'main', credentialsId: 'f0cbcf83-5935-4ae5-a0c6-3531b470b641', url: 'git@github.com:ruzina-0607/vector-role.git'
                }
            }
        }
        stage('install dependencies'){
            steps{
                dir('vector-role'){
                    sh 'pip3 install -r requirements.txt'
                }
            }
        }
        stage('run molecule'){
            steps{
                dir('vector-role'){
                    sh 'molecule test'
                }
            }
        }
    }
}
