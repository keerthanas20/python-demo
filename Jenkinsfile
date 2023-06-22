pipeline {
    agent { 
    label 'linux'
}
    
    stages {
        stage('Build') {
            steps {
                sh 'python -m venv venv' // Create a virtual environment
                sh '. venv/bin/activate' // Activate the virtual environment
                sh 'pip install -r requirements.txt' // Install dependencies
            }
        }
        
        stage('Test') {
            steps {
                sh 'python -m pytest' // Run tests
            }
        }
        
        stage('Package') {
            steps {
                sh 'python setup.py sdist bdist_wheel' // Create distribution packages
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'scp dist/*.tar.gz user@target-server:/path/to/deployment/' // Copy the package to the target server
                sh 'ssh user@target-server "pip install /path/to/deployment/*.tar.gz"' // Install the package on the target server
            }
        }
    }
}
