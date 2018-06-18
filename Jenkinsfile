pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn -e clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn -e test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven') {
                    sh 'mvn -e deploy'
                }
            }
        }
    }
}
