pipeline {
    
    agent any 
    
    environment {
        //The path of the code directory being fetched.
        DIRECTORY_PATH = "/var/lib/jenkins/workspace/first_pipeline"
        // The name of the testing environment.
        TESTING_ENVIRONMENT = "testingEnvironment"
        // My name
        PRODUCTION_ENVIRONMENT = "Monique"
    }
    stages {
// print a message that shows: 
// "fetch the source code from the directory path specified by DIRECTORY_PATH
// environment variable". 
// print this message:
//  "compile the code and generate any necessary artifacts".
        stage('Build') {
            steps {
                echo "fetch the source code from the directory path specified by the environment variable: ${DIRECTORY_PATH}"
                echo "compile the code and generate any necessary artefacts"
            }
            // post{
            //     always{
            //         echo "always"
            //     }
            //     success{
            //         echo "Build executed successfully"
            //     }
            //     failure{
            //         echo "Build execution failed"
            //     }
            // }
        }
//Add steps to print "unit tests" and "integration tests"messages.
        stage('Test') {
            steps {
                echo "unit tests"
                echo "integration tests"
            }
        }
// Add a message showing that "check the quality of the code".
        stage('Code Quality Check') {
            steps {
                echo "check the quality of the code"
            }
        }
// print "deploy the application to a testing environment".
// The environment name is specified by the environment variable.
        stage('Deploy') {
            steps {
                echo "deploy the application to a testing environment: ${TESTING_ENVIRONMENT}"
            }
        }
// add a sleep command to simulate manual approval. 
// The pipeline must pause for 10 seconds before continuing.        
        stage('Approval') {
            steps {
                echo "manual approval pending (simulated)"
                sleep 10
            }
        }
// add one step to show the related message to deploy the code to 
// the production environment using the environment variable 
// specifying the environment name.
        stage('Deploy to Production') {
            steps {
                echo "deploy code to the production environment: ${PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}

//     stages {

//         stage('Deploy') {
//             steps {
//                echo "$NAME, deployment is done"
//                 // timeout(time: 3, unit: 'SECONDS')
//                 // {
//                 //     sleep 5
//                 // }
//         }
//     }
// }