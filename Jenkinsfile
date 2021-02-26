pipeline{
    agent any
    stages {
        stage("build"){
            steps{
                echo "Executing Playbook"
                ansiblePlaybook(
                    inventory: '/Users/pavankumar/.jenkins/workspace/Ansible-Project/inventory',
                    playbook: '/Users/pavankumar/.jenkins/workspace/Ansible-Project/ansiblePlays/sample.yaml',
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