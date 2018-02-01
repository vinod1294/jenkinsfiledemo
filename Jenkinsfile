pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                //withMaven(maven : 'maven3.5.0') {
		     
		    bat 'set M2_HOME=C:\software\maven\apache-maven-3.5.0'
		    bat "set path =C:\software\maven\apache-maven-3.5.0\bin"
		    bat 'mvn -version'
                    bat 'mvn compile'
            //   }

			  
			  // Added new comment
		    // added new line
			}
        }

        stage ('Testing Stage') {

            steps {
               // withMaven(maven : 'maven3.5.0') {
                    
		    bat  'mvn test'
               // }
            }
        }


        stage ('Install Stage') {
            steps {
              //  withMaven(maven : 'maven3.5.0') {
                    bat 'mvn install'
               // }
            }
        }
    }
}
