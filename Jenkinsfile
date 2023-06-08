node {
    docker.image('maven:3.9.2').inside('-p 3000:3000') {
        stage('Build') {
            checkout scm
            sh 'mvn -B -DskipTests clean package'
        }
        stage('Test') {
            sh 'mvn test'
        }
    }
}