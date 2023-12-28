pipeline {
    agent any

    environment {
        GIT_REPO = 'https://github.com/your-username/your-repo.git'
        GIT_CREDENTIALS_ID = 'your-git-credentials-id'
        BRANCH_NAME = 'main'
    }

    stages {
        stage('init Repository') {
            steps {
                script {
                  sh 'git init'
                        }
            }
        }

        stage('Make Changes') {
            steps {
                script {
                    // Perform any necessary build or modification steps here
                    // For example, you might copy files, build your code, etc.
                    sh 'echo "Hello, Jenkins!" > newfile.txt'
                }
            }
        }

        stage('Commit and Push Changes') {
            steps {
                script {
                    // Add and commit changes
                    sh 'git add .'
                    sh 'git commit -m "Jenkins Pipeline commit"'

                    // Push changes back to the repository
                    sh 'git push origin main'
                }
            }
        }
    }

    post {
        always {
            // Clean up workspace after the pipeline execution
            cleanWs()
        }
    }
}
