pipeline{
    agent{
        label any
    }
    stages{
        stage("Restore dependencies"){
            when{
                anyOf {
                branch 'main'
                branch 'feature'
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
                    branch 'feature'
                }
            } 
            steps{
                bat "dontnet build --no-restore"
            }
        }
        stage("Run tests"){
            when{
                anyOf {
                    branch 'main'
                    branch 'feature'  
                } 
            }
            steps{
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}