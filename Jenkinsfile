pipeline {
    agent any

    stages {
        stage('Parallel Stages'){
            parallel{
                    stage('Build') {
                        steps {
                            echo 'Building..'
                        }
                    }
                    stage('Unit Test') {
                        steps {
                            echo 'BuUnit Test..'
                        }
                    }
            }
        }       
        stage('Sonar') {
            steps {
                echo 'Sonar Check..'
            }
        }
        stage('Docker Build') {
            steps {
                echo 'Docker Build..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('BDD') {
            when{
                expression { BRANCH_NAME ==~ /(jenkinsfilenew2|)/ }
            }
            steps {
                echo 'BDD Execution..'
            }
        }
        stage('Nexus Publishing') {
            when{
                expression { BRANCH_NAME ==~ /(master|release)/ }
            }
            steps {
                echo 'Publishing..'
            }
        }
        
    }
}