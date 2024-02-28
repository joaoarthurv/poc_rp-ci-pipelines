pipeline {
    agent any

    stages {
        stage("build"){
            steps {
            echo 'building the application...'
            echo 'Check pipe'
            sh "kubectl get configmap tfplan-default-pod-test-pr-9 -n faap-test -o yaml "
            }
        }

        stage("test"){
            steps {
            echo 'testing the application...'
            }
        }

        stage("deploy"){
            steps {
            echo 'deploy the application...'

            }
        }
    }
}