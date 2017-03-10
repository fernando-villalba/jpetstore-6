node {

    stage('checkout') {
        checkout scm
    }

    stage('build') {
        sh 'mvn clean install'

    }
    stage('archive') {
        junit 'target/surefire-reports'
        archiveArtifacts 'target/jpetstore.war'


    }

}
