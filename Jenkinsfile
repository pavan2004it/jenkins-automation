def gv
pipeline {
    agent any
    parameters{
        choice(name: 'VERSION', choices: ['1.1.0','1.2.0','1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    environment {
        NEW_VERSION = '1.3.0'
        // SERVER_CREDENTIALS = credentials('server-credentials')
    }
    stages {
        stage("init") {
            steps{
                script{
                    gv = load "script.groovy"
                }
            }
        }
        stage("build"){
            steps{
                script{
                    gv.buildApp()
                }
                echo "Executing Playbook"
                ansiColor('xterm'){
                    ansiblePlaybook(
                    installation: 'ansible',
                    inventory: 'inventory',
                    playbook: 'ansiblePlays/sample.yaml',
                    colorized: true
                )
                }
            }
        }

        stage("test"){
            steps{
                script{
                    gv.testApp()
                }
                echo "${NEW_VERSION}"
                withCredentials([
                    usernamePassword(credentialsId: 'server-credentials', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')
                ]) {
                    echo USERNAME
                }
                // echo "${SERVER_CREDENTIALS}"
            }
        }

        stage("deploy"){
            steps{
                script{
                    gv.deployApp()
                }
            }
        }


        
    }
}