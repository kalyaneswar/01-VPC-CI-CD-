pipeline{
    agent {
        label 'AGENT-1'
    }
    options{
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    parameters {
        choice(name: 'action', choices: ['Apply', 'Destroy'], description: 'Pick something')
    }

    stages{
        stage('Current Director with Shell'){
            steps{
                // Run multiple shell commands in a single 'sh' block
                    sh '''
                        echo "Current Directory:"
                        pwd
                    '''
                 }             
            }
            stage('List the files'){
            steps{
                // Run multiple shell commands in a single 'sh' block
                    sh '''
                        echo "list Directory:"
                        ls
                    '''
                 }             
            }
            stage('Init'){
            steps{
                // Run multiple shell commands in a single 'sh' block
                    sh '''
                        echo "Terraform init re-congiure:"
                        terraform init -reconfigure
                    '''
                 }             
            }
            stage('PLAN'){
                steps{
                // Run multiple shell commands in a single 'sh' block
                    sh '''
                        echo "Terraform plan:"
                        terraform plan
                    '''
                 }             
            }
            stage('Apply'){
                
                input {
                    message "Should we continue?"
                    ok "Yes, we should."               
                }
                steps{
                    sh """"
                    echo "We are about it apply"

                    """
            }
        }
    }
    post{
         always { 
            echo 'I will always say Hello again!'
        }
        success{
            echo 'Only run the steps in post if the current Pipeline’s or stage’s run has a "success" status, typically denoted by blue or green in the web UI.'
        }
        failure{
            echo 'Only run the steps in post if the current Pipeline’s or stage’s run has a "failed" status, typically denoted by red in the web UI.'
        }
    }
    
}