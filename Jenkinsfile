pipeline {
    //agent { label 'Java'}
agent none
    parameters {
string(name: 'cmd', defaultValue: 'default', description: 'A sample string parameter')
booleanParam(name: 'SAMPLE_BOOLEAN', defaultValue: true, description: 'A boolean parameter')
choice(name: 'cmd1', choices: ['install', 'compile'], description: 'Choose one option')
}
   stages {
stage ('hello-world-war'){
    parallel {
        stage('Checkout') {
           agent { label 'Java'}
            steps {
                sh "rm -rf hello-world-war"
              sh "git clone https://github.com/vivek-co/hello-world-war"
              
            }
        }

        stage('Build') {
            agent { label 'Java'}
            steps {
                 sh "mvn clean package"
            }
        }

        stage('Deploy') {
            agent { label 'Java'}
            steps {
                 // Example deployment command
                 echo "Deploying application"
                 sh "sudo cp /home/slave1/workspace/hello-world-war-pipeline/target/hello-world-war-1.0.0.war /opt/apache-tomcat-10.1.49/webapps"
            }
        }
    }
}
}
}
