pipeline {
    
    agent any
    
    parameters {
        string defaultValue: 'master', description: 'This requires the branch name to be checked out', name: 'branch_name'
        choice choices: ['DEV', 'SIT', 'UAT'], description: 'Select one of the environment value', name: 'environment_name'
    }
    
    stages {
        
        stage('Code Checkout'){
            steps {
                git branch: '$branch_name', credentialsId: 'github-credentials', url: 'https://github.com/gkdevops/simple-reactjs-app.git'
            }
        }
        
        stage('NPM install') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('generate static content') {
            steps {
                sh 'npm run build'
            }
        }
        
    }
}
