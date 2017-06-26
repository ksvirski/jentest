pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                bat dotnet restore
		bat dotnet build --configuration "Release"
		bat dotnet publish --configuration "Release" src/Website/Website.csproj  --output published-website
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}