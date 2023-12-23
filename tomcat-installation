pipeline {
    agent any

    // Define variables at the pipeline level
    environment {
        TOMCAT_VERSION = '9.0.83' // Define the desired Tomcat version
        TOMCAT_URL = "https://downloads.apache.org/tomcat/tomcat-9/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz"
    }

    stages {
        stage('Install Tomcat') {
            steps {
                // No need to redefine variables here
                script {
                    // Optional: Print the URL to verify
                    echo "Tomcat URL: ${env.TOMCAT_URL}"
                }
            }
        }
        
        stage('Download Tomcat') {
            steps {
                // Use the TOMCAT_URL variable from environment
                script {
                    sh "wget ${env.TOMCAT_URL}"
                }
            }
        }

        stage('Extract Tomcat tarball') {
            steps {
                // Use the TOMCAT_VERSION variable from environment
                script {
                    sh "tar -zxvf apache-tomcat-${env.TOMCAT_VERSION}.tar.gz"
                }
            }
        }
    }
}
