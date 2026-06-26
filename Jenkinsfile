pipeline {
    agent any

    stages {
        stage("Restore dependencies"){
            when{
                anyOf {
                branch 'main'
            }
            } 
            steps{
                bat "dotnet restore"
            }
        }
        stage("Built the app"){
            when {
                anyOf {
                    branch 'main'
                }
            } 
            steps{
                bat "dotnet build --no-restore"
            }
        }
        stage("Run tests"){
            when{
                anyOf {
                    branch 'main'
                } 
            }
            steps{
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}