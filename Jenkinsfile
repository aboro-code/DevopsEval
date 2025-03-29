pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('Build'){
            steps{
                bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test'){
            steps{
                bat 'mvn test'
            }
        }
        stage('Deliver'){
            steps{
                script{
                    def output = bat(script: 'java -jar target/my-app-1.0-SNAPSHOT.jar', returnStdout: true)
                    echo "Output: ${output}"
                }
            }
        }
    }
}