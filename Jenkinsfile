pipeline {
    agent any

    environment {
        GIT_REPO = 'https://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@github.com/mohithdevops9/jenkins_pipelines.git'
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
                    sh 'git config --global user.email "mohithdevops9@gmail.com"'
                    sh 'git config --global user.name "mohithdevops9"'
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
