pipeline{
    agent any
    stages {
        stage("build"){
            steps{
                ansiblePlaybook(
                    inventory: 'inventory'
                    playbook: 'ansiblePlays/sample.yaml'
                )
                echo "Hello world"
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