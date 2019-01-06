// Allocate Build Node
node('master') {
    stage("Fetch Source Code") {
        git 'https://github.com/TrainingByPackt/Beginning-Continuous-Delivery-With-Jenkins'
    }   

    stage("Testing") {
        printMessage('Running Pipeline')
        sh 'python test_functions.py'
    }

    stage('Deployment') {
        if (env.BRANCH_NAME == 'master') {
            printMessage('Deploying the master branch')
        } else {
            printMessage('No deployment configured for this branch')
        }
        printMessage('Pipeline Complete')
    }
}

def printMessage(message) {
    echo "${message}"
}
