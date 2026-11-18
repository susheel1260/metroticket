
node {

    stage('Checkout') {
        echo 'Checking out source code from GitHub'

        git branch: 'main',
            url: 'https://github.com/sitakameshwari/metroticket.git'
    }

    stage('Build') {
        echo 'Building Metro Ticket Reservation System'

        bat 'mvn clean package -DskipTests'
    }

    stage('Test') {
        echo 'Executing Unit Test Cases'

        bat 'mvn test'
    }

    stage('Archive') {
        echo 'Archiving generated WAR file'

        archiveArtifacts artifacts: 'target/*.war',
                         allowEmptyArchive: false
    }

    echo 'Metro Ticket Pipeline Executed Successfully'
}
