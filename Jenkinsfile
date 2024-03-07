pipeline {
    agent any

    triggers {
        GenericTrigger(
            genericVariables: [
                [key: 'webhookBody', value: '$.']
            ],
            regexpFilterText: '$',
            printContributedVariables: true
        )
    }

    stages {
        stage("build") {
            steps {
                echo 'building the application...'
                echo 'Check pipeline'
                script {
                    echo "${env.webhookBody}"
                }
            }
        }

        stage("test") {
            steps {
                echo 'testing the application...'
            }
        }

        stage("deploy") {
            steps {
                echo 'deploy the application...'
            }
        }
    }

    post {
        always {
            script {
                // Construa o objeto JSON com o atributo 'passed'
                def jsonResponse = [:]
                jsonResponse['passed'] = true // ou false, dependendo do resultado do seu build

                // Converta o objeto JSON em uma string JSON
                def jsonString = groovy.json.JsonOutput.toJson(jsonResponse)

                // Defina o retorno do webhook como a string JSON
                currentBuild.description = jsonString
            }
        }
    }
}