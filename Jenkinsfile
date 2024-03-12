pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    // environment {
    //     packageVersion = ''
    //     nexusURL = '172.31.14.12:8081'
    // }
    parameters {
        string(name: 'version', defaultValue: '1.0.0', description: 'what is artifact version?')
        string(name: 'environment', defaultValue: 'dev', description: 'what is environment?')
    }

    stages {
        
        stage('Print version') {
            steps {
                sh """
                    echo "version:${params.version}"
                """

            }
        }
    }
    // post build
    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
        failure { 
            echo 'this runs when pipeline is failed, used generally to send some alerts'
        }
        success{
            echo 'I will say Hello when pipeline is success'
        }
    }
}