pipeline {
    agent any

    stages {
        stage('Clonando Repositório Git') {
            steps {
                git branch: 'main', url: 'https://github.com/kenuemura/jk-public-gh.git'
            }
        }
        
        stage('Construindo Imagem') {
            steps {
                sh 'docker build -t webapp:${BUILD_NUMBER} .'
            }
        }
        
        stage('Implantando Aplicação') {
            steps {
                sh 'docker run --rm -d -p 3000:3000 --name webapp_ctr webapp:${BUILD_NUMBER}'
            
            }
        }
    }
}
