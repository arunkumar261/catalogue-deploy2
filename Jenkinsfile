pipeline {
    agent {
        node {
            label 'Agent-1'
        }
    }

    options {
        timeout(time: 1, unit: 'HOURS')
        disableConcurrentBuilds()
    }

    parameters {
        string(name: 'version', defaultValue: '', description: 'What is the version to download artifact ?')
        string(name: 'environment', defaultValue: '', description: 'What is the environment for infra ?')
    }

    stages {
         stage('Print the version') {
            steps {
            sh """
                echo "version : ${params.version}"
                echo "version : ${params.environment}"
            """
            }
        }
    }
    post {
        always {
            echo "I will always say Hello"
            deleteDir()
        }
        failure {
            echo "I will say Hello only pipeline fails"
        }
        success {
            echo "I will say Hello only pipeline success"
        }
    }
}