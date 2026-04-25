pipeline {
    agent any

    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run Test Stage')
    }

    environment {
        VERSION = '1.0'
        APP_NAME = 'MyPipelineApp'
    }

    stages {

        stage('Build') {
            steps {
                echo "Building ${APP_NAME} version ${VERSION}"
            }
        }

        stage('Test') {
            when {
                expression { return params.executeTests }
            }
            steps {
                echo 'Testing..'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }

    post {
        always {
            echo 'Pipeline Finished Successfully!'
        }
    }
}
