pipeline{
    agent any
    stages {
        stage("build"){
            steps{
                echo "Executing Playbook"
                ansiblePlaybook(
                    inventory: 'inventory',
                    playbook: 'ansiblePlays/sample.yaml',
                    colorized: true
                )
                
            }
        }

        stage("test"){
            steps{
                echo "Hello test"
            }
        }
        stage("prod"){
            steps{
                echo "Hello prod"
            }
        }
    }
}