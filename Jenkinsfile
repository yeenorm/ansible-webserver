pipeline {
    agent { label "agentfarm" }
    stages {
        stage('Delete the workspace') {
            steps {
                cleanWs()
            }
        }
        stage('Installing Ansible') {
            steps {
                def exist = fileExists '/usr/bin/ansible'
                if (exists) {
                    echo "Skipping Ansible install - already installed"
                } else {}
                    echo "Installing Ansible"
                    sh 'sudo apt-get update -y'
                    sh 'sudo apt-get upgrade -y'
                    sh 'sudo apt install -y wget tree unzip ansible python3-pip python3-apt'
            }
        }
        stage('Third Stage') {
            steps {
                echo "Third stage"
            }
        }
    }
}
