node {
    docker.image('maven:3.8.5-eclipse-temurin-8-alpine').inside('-p 3000:3000 -v /root/.m2:/root/.m2') {
        stage('Build') {
            checkout scm
            sh 'mvn -X -B -DskipTests clean package'
        }
        stage('Test') {
            sh 'mvn test'
        }
    }
}