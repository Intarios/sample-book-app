pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    build()
                }
            }
        }
        stage('Deploy to DEV') {
            steps {
                script {
                    deploy("DEV")
                }
            }
        }
        stage('Tests on DEV') {
            steps {
                script {
                    test("DEV")
                }
            }
        }
        stage('Deploy to STG') {
            steps {
                script {
                    deploy("STG")
                }
            }
        }
        stage('Tests on STG') {
            steps {
                script {
                    test("STG")
                }
            }
        }
        stage('Deploy to PROD') {
            steps {
                script {
                    deploy("PROD")
                }
            }
        }
        stage('Tests on PROD') {
            steps {
                script {
                    test("PROD")
                }
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

def build()
{
    echo "Building of node application is starting .."
}

def deploy(String environment)
{
    echo "Deployment to ${environment} has started .."
}

def test(String environment)
{
    echo "Testing on ${environment} has started .."
}

