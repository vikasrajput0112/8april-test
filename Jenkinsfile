pipeline {
    agent any

    stages {
        stage('Create File') {
            steps {
                script {
                    // Create a file named paisalo and write "It is a bank" to it
                    touch paisalo
                    echo "hello this is a bank" >> paisalo
                }
            }
        }

        stage('Verify File Creation') {
            steps {
                script {
                    // Print the content of the file to the Jenkins console
                    def content = readFile('paisalo')
                    echo "File content: ${content}"
                }
            }
        }
    }
}
