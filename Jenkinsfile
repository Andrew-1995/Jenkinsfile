pipeline {
    agent any
    parameters {
        

        

        booleanParam(name: 'VM_TEST', defaultValue: false, description: 'Checkbox paramete')

        booleanParam(name: 'VM_LIVE', defaultValue: false, description: 'Checkbox paramete')

    }
    stages {
        stage('Test') {
            when {
                expression {VM_TEST == 'true'}
            }
            steps {
                git url: 'https://github.com/HoussemDellai/angular-app-kubernetes.git'
                sh 'docker build -t 3226555/angular:angular-2 .'
                kubernetesDeploy(configs:'deployment.azure.yaml', kubeconfigId:'Kubernetes_Credential',enableConfigSubstitution: true)
                echo "Click here to Deploy on VM Test: ${params.VM_TEST}" 
            }
        }
        stage('Live') {
            when {
                expression {VM_LIVE == 'true'}
            }
            steps {
                echo "Click here to Deploy on VM Live: ${params.VM_LIVE}"
            }
        }
    }
}
