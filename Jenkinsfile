pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Use Maven or Gradle to build the application
                sh 'mvn clean package'
            }
        }
        stage('Unit Test') {
            steps {
                // Run unit tests using the appropriate command
                sh 'mvn test'
            }
        }
        stage('Artifact Packaging') {
            steps {
                // Package the application into a JAR file or Docker image
                sh 'mvn package'
                // Or build Docker image: sh 'docker build -t myapp .'
            }
        }
      /*
        stage('Deployment') {
            steps {
                // Use SSH to copy the artifact to AWS EC2 and start the application
                sshagent(['my-ssh-credentials']) {
                    sh 'scp target/myapp.jar ec2-user@<EC2-Instance-IP>:~/'
                    sh 'ssh ec2-user@<EC2-Instance-IP> "java -jar ~/myapp.jar &"'
                }
            }
        }
    }
    post {
        success {
            // Send success notification (e.g., Slack or Email)
            echo 'Deployment successful! Send notification...'
        }
        failure {
            // Send failure notification (e.g., Slack or Email)
            echo 'Deployment failed! Send notification...'
        }
    }
    */
    }
}
