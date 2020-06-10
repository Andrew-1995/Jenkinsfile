pipeline {
    agent any
    parameters {
        

        

        booleanParam(name: 'VM_TEST', defaultValue: false, description: 'Checkbox paramete')

        booleanParam(name: 'VM_LIVE', defaultValue: false, description: 'Checkbox paramete')

    }
    stages {
        stage('Test') {
            steps {
                echo "Click here to Deploy on VM Test: ${params.VM_TEST}" 
            }
        }
        stage('Live') {
            steps {
                echo "Click here to Deploy on VM Live: ${params.VM_LIVE}"
            }
        }
    }
}
