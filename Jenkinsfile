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
               
               bat 'npm run clean'
               bat 'npm run build'
            }

            stage('Test') {
                steps {
                    parallel(
                        a: {
                            echo "This is a branch a"
                        },

                        b: {
                            echo "This is a branch b"
                        }
                    )
                }
                bat 'echo Testing...'
                bat 'npm test'
            }
            
            stage('Deployment'){
                bat 'echo Deployment...'
                bat 'npm start'
            }



}
