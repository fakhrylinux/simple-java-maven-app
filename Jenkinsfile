node {
    docker.image('arm64v8/maven:3.9-eclipse-temurin-11-focal').inside('-p 3000:3000 -v /root/.m2:/root/.m2') {
        stage('Build') {
            checkout scm
            sh 'mvn -X -B -DskipTests clean package'
        }
        stage('Test') {
            sh 'mvn test'
        }
        stage('Deploy') {
            input message: 'Lanjutkan ke tahap Deploy?' 
            sh './jenkins/scripts/deliver.sh'
        }
    }
}