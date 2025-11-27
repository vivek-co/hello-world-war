pipeline {
    agent { label 'Java'}

    stages {

        stage('Checkout') {
            steps {
                sh "rm -rf hello-world-war"
              sh "git clone https://github.com/vivek-co/hello-world-war"
              
            }
        }

        stage('Build') {
            steps {
                 sh "mvn clean package"
            }
        }

        stage('Deploy') {
            steps {
                 // Example deployment command
                 echo "Deploying application"
                 sh "sudo cp /home/slave1/workspace/hello-world-war-pipeline/target/hello-world-war-1.0.0.war /opt/apache-tomcat-10.1.49/webapps/hello-world.war"
            }
        }
    }
}
