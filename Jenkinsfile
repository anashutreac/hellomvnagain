pipeline {
    agent {
        node {
            label 'Slave03'
        }
    }
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
                 script {
                    version = sh(returnStdout: true, script: 'mvn help:evaluate -Dexpression=project.version | grep -e "^[^[]" ')
                 }
               echo version
            }
        }

        stage("Tests") {
             steps {
                /* sh 'mvn clean install' */
                sh 'mvn test'
                echo version
            }
        }

        stage("Deploy") {
             steps {
                /* sh 'mvn clean install' */
                sh 'mvn package'
                echo version
            }
        }
    }
}
