node('testing') {
    stage('Initialize') {
        echo 'Initializing...'
        def node = tool name: 'Node-5.6.0', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
        env.PATH = "${node}/bin:${env.PATH}"
    }

    stage('Checkout') {
        echo 'Getting source code...'
        checkout scm
    }

    stage('Build') {
        echo 'Building dependencies...'
        bat 'npm i'
    }

    stage('Test') {
        echo 'Testing...'
        bat 'npm test'
    }
}
