pipeline {
    agent any
    tools {
        nodejs "Node"
    }
    stages {
        stage('Clone Repository') {
            steps {
                git credentialsId: '155ee78d-2be8-420c-9f7c-e5388f918657', url: 'https://github.com/Atombarane/Reactjs-sample.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                bat 'xcopy "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\Reactpipeline\\build\\*" "C:\\inetpub\\wwwroot\\React\\" /E /I /H /Y'
            }
        }
    }
}
