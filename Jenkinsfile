pipeline{
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        stage('SCM checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/aswin615/SpringPetClinic.git'
            }
        }
        stage('Compile'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarative/target/*.jar'
            }
        }
    }
}
