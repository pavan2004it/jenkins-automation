pipeline{
    agent any
    stages {
        stage("build"){
            steps{
                ansiblePlaybook('ansiblePlays/sample.yaml'){
                    inventoryPath('inventory') 
                }
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