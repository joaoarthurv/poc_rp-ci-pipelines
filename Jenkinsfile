pipeline {
    agent any

    stages {
        stage("build"){
            steps {
            echo 'building the application...'
            echo 'Check pipe'
            echo 'call TF Controller to get plan'

            echo "Debug: PATH is $PATH"
            which kubectl
            kubectl version --client

            echo 'kubectl config view...'

            export KUBECONFIG=/var/jenkins_home/.kube/config

            kubectl config view

            kubectl get nodes

            echo 'Obtendo o ID do plano do TF Controller...'
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