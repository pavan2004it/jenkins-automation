pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('server-credentials')
    }
    stages {
        stage("build"){
            steps{
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
                echo "${NEW_VERSION}"
                echo "${SERVER_CREDENTIALS}"
            }
        }
        
    }
}