pipeline {
    agent {label build}
       stages 
    {
        stage('checkout') {             
            steps {
                sh 'https://github.com/Charanraj2498/hello-world-war.git'
            }
        }
         stage('build') { 
            steps {
                sh 'cd hello-world-war'
                sh 'mvn clean package'
            }
        }
    }
}
