node {
    stage('Initialize') {
        echo 'echo Initializing...'
        def node = tool name: 'Node-8.9.0', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
        env.PATH = "${node}/bin:${env.PATH}"
    }

    stage('Checkout') {
        echo 'echo Getting source code...'
        checkout scm
    }

    stage('Build') {
        echo 'echo Building dependencies...'
        bat 'npm i'
    }

    stage('Test') {
        bat 'echo Testing...'
        bat 'npm test'
    }
}
