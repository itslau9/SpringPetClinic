pipeline {
    agent{label 'master'}
    tools{maven 'M3'}
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/itslau9/SpringPetClinic.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
