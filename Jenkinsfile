pipeline {
    
    agent any
    
    parameters {
        string defaultValue: 'master', description: 'This requires the branch name to be checked out', name: 'branch_name'
        choice choices: ['DEV', 'SIT', 'UAT'], description: 'Select one of the environment value', name: 'environment_name'
    }
    
    stages {
        
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
