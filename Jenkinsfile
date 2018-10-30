pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                bat 'set M2_HOME  = C:/temp/apache-maven-3.5.4
                set path=C:/temp/apache-maven-3.5.4/bin:%path%
                mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}