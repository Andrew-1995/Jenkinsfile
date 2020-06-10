pipeline {
    agent any
    parameters {
        

        

        booleanParam(name: 'VM_TEST', defaultValue: false, description: 'Checkbox paramete')

        booleanParam(name: 'VM_LIVE', defaultValue: false, description: 'Checkbox paramete')

    }
    stages {
        stage('Example') {
            steps {
                

                echo "Click here to Deploy on VM Test: ${params.VM_TEST}"

                

               
            }
            
            steps{
                echo "Click here to Deploy on VM LIVE: ${params.VM_LIVE}"
                
            }
        }
    }
}
