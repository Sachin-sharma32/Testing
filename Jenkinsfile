// create a pipeline
pipeline{
    // agent is similar to container
    // it's an environment where jobs run
    agent any // use any agent available 

    // there are total 5 stages in pipeline
    // 1) connect to github project
    // 2) run client tests
    // 3) run server tests
    // 4) build docker image
    // 5) push to dockerhub

    stages{
        // STAGE 1
        //-> sudo yum install git (install git on our ec2 machine)
        //-> click create a new pipeline in "blue ocean" plugin in jenkins
        //-> select github 
        stage('Checkout'){  // name of step
            steps{
                checkout scm // checkout repo using SCM (source code management system i.e. git)
            }
        }
    }
}