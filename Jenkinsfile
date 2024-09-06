pipeline{
    agent {
        label 'AGENT-1'
    }
    options{
        timeout(time: 1, unit: 'HOURS')
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