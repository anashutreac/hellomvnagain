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
