pipeline {
    agent any

    stages {
	  echo "branch name  ${env.JOB_NAME}"
	 // (env.BRANCH_NAME == 'develop'
	  if(env.JOB_NAME == 'jenkinsfile-jobname'){
        stage ('Compile Stage') {

            steps {
               // withMaven(maven : 'maven3.3.9') {
                    bat 'mvn clean compile'
              //  }
            }
        }}

        stage ('Testing Stage') {

            steps {
              //  withMaven(maven : 'maven3.3.9') {
                    bat 'mvn test'
               // }
            }
        }


        stage ('Deployment Stage') {
            steps {
              //  withMaven(maven : 'maven3.3.9') {
                    bat 'mvn install'
               // }
            }
        }
    }
}