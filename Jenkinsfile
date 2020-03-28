pipeline {
    stages {
        stage('Build') { 
            steps {
                def mvnHome = tool name: 'maven_3', type: 'maven'
                sh '${mvnHome}/bin/mvn -B -DskipTests clean package' 
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}