pipeline {
    agent {label build}
       stages 
    {
        stage('checkout') {             
            steps {
                sh 'git clone https://github.com/hhgsharish/hello-world-war/'
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
