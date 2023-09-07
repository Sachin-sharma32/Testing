// create a pipeline
pipeline {
    // agent is similar to container
    // it's an environment where jobs run
    agent any // use any agent available

    // there are total 5 stages in pipeline
    // 1) connect to github project
    // 2) run frontend tests
    // 3) run backend tests
    // 4) build docker image
    // 5) push to dockerhub

    stages {
        // STAGE 1
        //-> sudo yum install git (install git on our ec2 machine)
        //-> click - create a new pipeline in "blue ocean" plugin in jenkins
        //-> select github - select repo
        stage('Checkout') {  // name of step
            steps {
                checkout scm // checkout repo using SCM (source code management system i.e. git)
            }
        }

        // STAGE 2
        // stage('Client Tests') {
        //     steps {
        //         dir('docker-react') {
        //             sh 'npm install'  // sh -> means run in the shell
        //             sh 'npm test'   // you have to manually add tests and provide this scripe in package.json
        //             // first install nodejs on ec2 instance and commit this code and retart the jenkins pipeline
        //         }
        //     }
        // }
    }
}
