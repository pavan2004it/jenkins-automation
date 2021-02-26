pipeline {
    agent any
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
        
    }
}