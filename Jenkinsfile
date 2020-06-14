pipeline {
    agent any
    parameters {
        

        

        booleanParam(name: 'VM_TEST', defaultValue: false, description: 'Checkbox paramete')

        booleanParam(name: 'VM_LIVE', defaultValue: false, description: 'Checkbox paramete')

    }
    stages {
        stage('CheckOut') {
            steps {
                git url: 'https://github.com/Andrew-1995/spring-boot-mongo-docker-.git'
                } 
            }
        
        stage('Build Project MVN') {
            steps {
                def mvnHOME = tool name: 'maven-3', type: 'maven'
                def mvnCMD = "${mvnHOME}/bin/mvn"
                sh "${mvnCMD} clean package"
            }
        }
        stage('Build image'){
            steps{
                sh 'docker build -t 3226555/angular:2020 .'
            }
        }
        stage('Deploy to K8s'){
            steps{
                kubernetesDeploy(
                configs:'springBootMongo.yml',
                kubeconfigId:'Kubernetes_Credential',
                enableConfigSubstitution: true)
            }
        }
    }
}
