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
                git url: 'https://github.com/Andrew-1995/spring-boot-mongo-docker-.git'
                def mvnHOME = tool name: 'maven-3', type: 'maven'
                def mvnCMD = "${mvnHOME}/bin/mvn"
                sh "${mvnCMD} clean package"
                


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
