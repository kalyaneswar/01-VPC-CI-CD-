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
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
            stage('Parameters') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
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