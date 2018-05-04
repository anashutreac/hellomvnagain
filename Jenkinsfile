pipeline {
    agent any
    stages {
        
        stage("Clean") {
            steps {
                echo 'Cleaning...'
               /* deleteDir() clean up our workspace */
            }
        }
        stage("Checkout") {
             steps {
                echo 'Cleaning...'
            }
        }
        stage("Build") {
             steps {
                /* sh 'mvn clean install' */
                sh 'mvn install -DskipTests'
               def version = sh(returnStdout: true, script: 'mvn help:evaluate -Dexpression=project.version | grep -e \'^[^\[]\'')
                sh 'echo version'
            }
        }

        stage("Tests") {
             steps {
                /* sh 'mvn clean install' */
                sh 'mvn test'
            }
        }

        stage("Deploy") {
             steps {
                /* sh 'mvn clean install' */
                sh 'mvn package'
            }
        }
    }
}
