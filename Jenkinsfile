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
                    deploy("DEV", 1010)
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
                    deploy("STG", 1020)
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
                    deploy("PROD", 1030)
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
    bat "dir /b /a-d"
    script {
        pm2("install")
    }
}

def deploy(String environment, int port)
{
    echo "Deployment to ${environment} has started .."

    script {
        pm2("delete ${environment}")
        pm2("start -n \"${environment}\" index.js -- ${port}")
    }
}

def test(String environment)
{
    echo "Testing on ${environment} has started .."
    script {
        pm2("test")
    }
}

def pm2(String command)
{
    bat "\\node_modules\\.bin\\pm2 ${command}"
}
