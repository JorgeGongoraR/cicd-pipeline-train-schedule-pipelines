pipeline{
    agent any

    stages{
        stage("Executes the gradle build"){
            steps{
                echo "========executing glade build========"
                sh './gradlew build --no-daemon'
            }
        }
        // stage("Run the app"){
        //     steps{
        //         echo "========running the app========"
        //         sh './gradlew npm start'
        //     }
        // }
        stage("Archives the dist/trainSchedule.zip artifact."){
            steps{
                echo "========Archiving========"
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }     
    }
}