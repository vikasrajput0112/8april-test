pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Clone the repository or check out the source code
                    checkout scm
                }
            }
        }

        stage('Remove Git') {
            steps {
                script {
                    // Remove the .git directory from the workspace
                    def gitDir = "${env.WORKSPACE}/.git"
                    if (fileExists(gitDir)) {
                        echo "Removing Git directory..."
                        deleteDir()  // Deletes the entire workspace, including the .git folder
                    } else {
                        echo "No Git repository found to remove."
                    }
                }
            }
        }
    }

    post {
        always {
            echo 'Cleaning up the workspace.'
        }
    }
}
