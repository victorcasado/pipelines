pipeline {
    def username = 'Jenkins'
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Hello Mr. ${username}'
                echo "I said, Hello Mr. ${username}"
            }
        }
    }
}
