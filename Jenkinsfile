pipeline {
    agent any
    
    tools {
        jdk "java17"
        maven "maven3"
    }

    stages {
        stage('Build Code') {
            steps {
                echo "Building the code..."
                sh 'mvn clean package'
            }
        }
    

        stage('Archive Artifact') {
            steps {
                echo "Archiving WAR file..."
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }
    }
}
