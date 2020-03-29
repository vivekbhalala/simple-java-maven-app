node {
        stage('Build') { 
                def mvnHome = tool name: 'maven_3', type: 'maven'
                sh "${mvnHome}/bin/mvn -B -DskipTests clean package"  
        }
        stage('Test') {
                def mvnHome = tool name: 'maven_3', type: 'maven'
                sh "${mvnHome}/bin/mvn clean install"
        }
}