pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out code from repository...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage (no compilation needed for Python)'
                sh 'python3 --version'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh '''
python3 - <<EOF
from calculator import add, multiply, subtract, divide

print("Running Calculator Tests...")
print("--------------------------------")

print("add(2,3) =", add(2,3))
print("multiply(2,3) =", multiply(2,3))
print("subtract(5,2) =", subtract(5,2))
print("divide(10,2) =", divide(10,2))

print("--------------------------------")

assert add(2,3) == 5
assert multiply(2,3) == 6
assert subtract(5,2) == 3
assert divide(10,2) == 5

print("All tests passed successfully!")
EOF
'''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage (dummy)'
            }
        }
    }
}
