node {
        // stage('Checkout') { 
        //         git 'https://github.com/vivekbhalala/simple-java-maven-app.git'  
        // }
        stage('Build') { 
                def mvnHome = tool name: 'maven_3', type: 'maven'
                sh "${mvnHome}/bin/mvn -B -DskipTests clean package"  
        }
        stage('Test') {
                def mvnHome = tool name: 'maven_3', type: 'maven'
                sh "${mvnHome}/bin/mvn clean install"
        }
}