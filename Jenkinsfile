pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/hady-potter/jenkins-python-project.git'
            }
        }

        stage('Install Requirments') {
            steps {
                echo "Installing the Requirments"
                sh 'pip install -r requirements.txt'
                echo "Installation finished"
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                sh 'python3 -m unittest discover test'
                echo "Testing done"
            }
        }
        
        stage('Run') {
            steps {
                echo "Running the project..."
                sh 'python3 app/data_processor.py'
            }
        }
        
        

        stage('Deploy') {
            steps {
                echo "Deploying application (simulation)..."
            }
        }
    }

    post {
        success {
            echo "Pipeline completed successfully!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}
