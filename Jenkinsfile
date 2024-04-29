pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building of node application is starting .."
            }
        }
        stage('Deploy to DEV') {
            steps {
                echo "Deployment to DEV has started .."
            }
        }
        stage('Tests on DEV') {
            steps {
                echo "Testing on DEV has started .."
            }
        }
        stage('Deploy to STG') {
            steps {
                echo "Deployment to STG has started .."
            }
        }
        stage('Tests on STG') {
            steps {
                echo "Testing on STG has started .."
            }
        }
        stage('Deploy to PROD') {
            steps {
                echo "Deployment to PROD has started .."
            }
        }
        stage('Tests on PROD') {
            steps {
                echo "Testing on PROD has started .."
            }
        }

    }
}


// Build of application;
//  deployment in “DEV” env;
// Test execution against DEV env;
//  deployment in “STG” env;
// Test execution against STG env;
//  deployment in “PRD” env;
// Test execution against PRD env.
