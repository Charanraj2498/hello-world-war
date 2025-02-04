pipeline {
    agent none
    environment { 
    ARTIFACTORY_CREDENTIALS = credentials('jfrog-credentials')
    }
       stages 
    {
        stage('checkout') {    
            agent {label 'build'}
            steps {
                git 'https://github.com/Charanraj2498/hello-world-war.git'
            }
        }
         stage('build') { 
             agent {label 'build'}
            steps {
                sh 'mvn clean package'
            }
        }
        stage('publish') { 
            agent {label 'build'}
            steps {
               sh 'mkdir -p ~/.m2'
               sh '''
                 echo "<settings>
                          <servers>
                            <server>
                              <id>helloworldwar</id>
                              <username>$ARTIFACTORY_CREDENTIALS_USR</username>
                              <password>$ARTIFACTORY_CREDENTIALS_PSW</password>
                      </server>
                     </servers>
                   </settings>" > ~/.m2/settings.xml
              '''
            sh 'cat ~/.m2/settings.xml'    
            sh 'mvn clean deploy'
        
            }
        }
    }
}
