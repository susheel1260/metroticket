
node {
    stage('Checkout') {
        echo 'Checking out source code'
        git branch: 'main',
            url: 'https://github.com/sitakameshwari/metroticket.git'
    }

    stage('Build') {
        echo 'Building Metro Ticket Application'
        sh 'mvn clean package -DskipTests'
    }

    stage('Test') {
        echo 'Running Unit Tests'
        sh 'mvn test'
    }

    stage('Archive') {
        echo 'Archiving build artifacts'
        archiveArtifacts artifacts: 'target/*.jar,target/*.war',
                         allowEmptyArchive: false
    }
}
