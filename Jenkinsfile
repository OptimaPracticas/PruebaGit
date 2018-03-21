node {
    stage('Initialize') {
        bat 'echo Initializing...'
        def node = tool name: 'Node-8.9.0', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
        env.PATH = "${node}/bin:${env.PATH}"
    }

    stage('Checkout') {
        bat 'echo Getting source code...'
        checkout scm
    }

    stage('Build') {
        bat 'echo Building dependencies...'
        bat 'npm i'
    }

    stage('Test') {
        bat 'echo Testing...'
        bat 'npm test'
    }

    stage('Publish') {
        echo 'Publishing Test Coverage...'
		publishHTML (target: [
			allowMissing: false,
			alwaysLinkToLastBuild: false,
			keepAll: true,
			reportDir: 'coverage/lcov-report',
			reportFiles: 'index.html',
			reportName: "Application Test Coverage"
		])
    }
}
