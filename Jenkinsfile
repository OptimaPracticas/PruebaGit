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

            stage('Dependencies') {
                bat 'echo Building dependencies...'
                bat 'npm i'
            }

            stage('Test') {
                bat 'echo Testing with try/catch...'
                bat 'npm test'
            }
            stage('Start') {
                bat 'echo Stopping...'
                //bat 'npm stop'
                bat 'echo Build...'
                bat 'npm start'
            }
            //Manuel
        }
    }catch(e){
        println 'ERROR'
    }finally{
        bat 'npm stop'
        println 'Finally'
    }