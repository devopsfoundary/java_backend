pipeline {
      agent {
            label 'slave1'
            }
      stages {
            stage('Checkout') {
                  steps {
                        echo 'Hi, this is our first Pipeline Job'
                        git 'https://github.com/devopsfoundary/java_backend.git'
                  }
            }
            stage('Build') {
                  steps {
                        echo 'Building Sample Maven Project'
                        sh "mvn -Dmaven.test.failure.ignore=true clean package"            
                  }
            }
            stage('Deploy') {
                  steps {
                        echo "Deploying in Testing Server"
                        echo "Deploying in Testing2 Server"
                        sh "cp $WORKSPACE/target/demo.war /home/ubuntu/Deployments"
                        
                  }
            }
            stage('Deploy to Stage') {
                  steps {
                        echo "Deploying in Stage Server"
                  }
            }
      }
}
