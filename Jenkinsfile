node {

    stage('checkout') {
        checkout scm
    }

    stage('build') {
        sh 'mvn clean install'

    }
    stage('archive') {
        junit 'target/surefire-reports/*.xml'
        archiveArtifacts 'target/jpetstore.war'

    }

    stage('SonarQube analysis') {
        // requires SonarQube Scanner 2.8+

        def scannerHome = tool 'GreatScanner';
        withSonarQubeEnv('Sonarqube') {
            sh "${scannerHome}/bin/sonar-scanner"

        }

    }

}
