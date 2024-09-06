pipeline{
    agent {
        label 'AGENT-1'
    }
    options{
        timeout(time: 1, unit: 'HOURS')
    }

    stages{
        stage('Current Director with Shell'){
             // Run multiple shell commands in a single 'sh' block
                    sh '''
                        echo "Building..."
                        pwd
                        echo "Current Dir in shell"
                    '''
        }
        stage('Current Director with Groovy'){
            script{
                 // Run multiple Groovy commands
                    echo "Building..."
                    pwd
                    echo "This is dir with Groovy"
                    // Add more Groovy commands or logic here
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