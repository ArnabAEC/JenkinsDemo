pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "mvn38"
	jdk   "jdk18"
    }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://bitbucket.org/java_kumar_arun/jenkinspipelinedemo'

                // Run Maven on a Unix agent.
               // bat "mvn -Dmaven.test.failure.ignore=true clean package"
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
        stage('Compile') {
            steps {
                // Get some code from a GitHub repository
                //git 'https://bitbucket.org/java_kumar_arun/jenkinspipelinedemo'

                // Run Maven on a Unix agent.
                bat "mvn -Dmaven.test.failure.ignore=true clean compile"
                // bat "mvn -Dmaven.test.failure.ignore=true clean compile"
            }
		}
    	stage('Test') {
            steps {
                // Get some code from a GitHub repository
                //git 'https://bitbucket.org/java_kumar_arun/jenkinspipelinedemo'

                // Run Maven on a Unix agent.
                bat "mvn -Dmaven.test.failure.ignore=true clean test"
                // bat "mvn -Dmaven.test.failure.ignore=true clean install"
            }
		}
		stage('Package') {
            steps {
                // Get some code from a GitHub repository
                //git 'https://bitbucket.org/java_kumar_arun/jenkinspipelinedemo'

                // Run Maven on a Unix agent.
                bat "mvn -Dmaven.test.failure.ignore=true clean package"
                // bat "mvn -Dmaven.test.failure.ignore=true clean install"
            }	
		}

    }

            post{
                // If Maven was able to run the tests, even if some of the test
                // failed, record the test results and archive the jar file.
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'mail bcc: '', body: 'Just a mail from jenkins', cc: '', from: '', replyTo: '', subject: '', to: 'anysome3@gmail.com'
                }
        }
    }

