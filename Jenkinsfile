try{
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
                bat 'echo Testing with try/catch...'
                bat 'npm test'
            }

            //Manuel
        }
    }catch(e){
        println 'ERROR'
    }finally{
        println 'Finally'
    }