pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                // Fetch the code from the repository
                git url: "https://github.com/btechconsults/NewsletterRepo.git"   
				
			}
		}
        stage('Install Apache Server') {
            steps {
                script {
                    echo "sudo install Apache Server"
                   // sh 'sudo apt install apache2 -y'
                }
            }
        }

        stage('Deploy Web Page') {
            steps {
                script {
                    echo "Copy the fetched code (web page) to the Apache web directory"
                    sh 'cp -R * /var/www/html/'
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment was successful!'
        }
        failure {
            echo 'Deployment failed. Please check the logs.'
        }
    }
}
