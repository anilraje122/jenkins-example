pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn deploy'
                }
                withMaven(maven : 'maven') {
                    sh 'sudo /bin/cp /var/lib/jenkins/workspace/jenkins-pipeline-17jun2018/target/jenkins-example-1.0-SNAPSHOT.jar /var/lib/tomcat7/webapps/'
                }
            }
        }
    }
}
