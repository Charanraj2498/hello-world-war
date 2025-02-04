pipeline {
    agent {label 'build'}
       stages 
    {
        stage('checkout') {             
            steps {
                git 'https://github.com/Charanraj2498/hello-world-war.git'
            }
        }
         stage('build') { 
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
