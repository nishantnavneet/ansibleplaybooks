pipeline{
    agent any
    stages{
        stage('SCM Checkout'){
            steps{
                git branch: 'main', credentialsId: '95189103-9f8f-4af3-b274-375e2cd713bf', url: 'https://github.com/nishantnavneet/ansibleplaybooks.git'
            }
        }
        stage('Package to install'){
            steps{
                sh 'echo ${package}'
            }
        }
        stage('Execute Ansible'){
            steps{
                ansiblePlaybook become: true, colorized: true, credentialsId: '1135500c-bfb4-4b83-beb9-fd2aba35b515', disableHostKeyChecking: true, extras: '-e pkg=${package}', installation: 'ansible', inventory: 'inventory', playbook: 'package.yml'
            }
        }
    }
}
