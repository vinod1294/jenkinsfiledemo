pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
               // withMaven(maven : 'maven3.3.9') {
                    sh 'mvn clean compile'
              //  }

			  
			  // Added new comment
		    // added new line
			}
        }

        stage ('Testing Stage') {

            steps {
              //  withMaven(maven : 'maven3.3.9') {
                    sh  'mvn test'
               // }
            }
        }


        stage ('Deployment Stage') {
            steps {
              //  withMaven(maven : 'maven3.3.9') {
                    sh 'mvn install'
               // }
            }
        }
    }
}
