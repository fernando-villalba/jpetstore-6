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

}
