pipeline{
    agent any
    tools {
        glade "1.36"
    }
    
    options {
        timeout(time: 2, unit: 'MINUTES')
    }

    stages{
        stage("Executes the gradle build"){
            steps{
                echo "========executing glade build========"
                sh './gradlew build --no-daemon'
            }
        }
        stage("Run the app"){
            steps{
                echo "========running the app========"
                sh './gradlew npm_start'
            }
        }
        stage("Archives the dist/trainSchedule.zip artifact."){
            steps{
                echo "========Archiving========"
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }     
    }
}