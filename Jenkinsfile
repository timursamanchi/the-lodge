pipeline{
    agent any
    // all jobs will be running om jenkins-slave
    environment {
        MAX_SIZE = 100
        MIN_SIZE = 10
    }
    parameters {
        choice ( name: 'Environment', 
            choices: ['production', 'development','staging'],
            description: 'please select an enviroment for this depolyment')
        string ( name: 'Email_Address',
            defaultValue: 'name.surname@domain.com',
            description: 'enter your email address')
        booleanParam ( name: 'RUN_TESTS',
            defaultValue: false,
            description: 'Run tests and obtain explicit approval before full deployement')    
    }
    stages{
        stage('build'){
            steps {
                echo "Build stage"
                sh 'echo "this is a report" > report.txt'
                sh "echo Run test: \"${params.RUN_TESTS}\" >> report.txt"
            }
        }
        stage ('deploy'){
            when {
                // if deployment environment is production = true
                expression { params.Environment == 'production' }
            }
            steps {
                echo "this is MAX = ${env.MAX_SIZE}"
                echo "this is MIN = ${env.MIN_SIZE}"
                input message: 'Confirm deployment to production...', ok: 'Deploy'
                echo "Deploying to ${params.Enviroment}"
                sh "echo this is MIN = \"${params.Enviroment}\" >> report.txt"  
            }
        }
        stage ('report'){
            steps {
                echo "this is your email address ${params.Email_Address}"
                sh 'echo "Reporting stage - TEST TEST" >> report.txt'
                sh "echo \"${params.Email_Address}\" >> report.txt"
                sh "printf \"${params.RUN_TESTS}\" > ${env.MAX_SIZE}.txt"
                archiveArtifacts allowEmptyArchive: true, artifacts: '*.txt', fingerprint: true, followSymlinks: false, onlyIfSuccessful: true
            }
        }
    }
}