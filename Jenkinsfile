pipeline {
    agent any
    parameters {
        choice(name:'door_choice' , choices: 'one\ntow\nthree\nfour',description: 'what door do u choos?')
        

        

        booleanParam(name: 'CAN_DANCE', defaultValue: true, description: 'Checkbox paramete')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        string(name: 'sTrAnGePaRaM', defaultValue: 'Dance!', description: 'Do the funky chicken')
    }
    stages {
        stage('Example') {
            steps {
                echo ' Hello '

                echo "Trying: ${params.door_choice}"

                echo "We can dance: ${params.CAN_DANCE}"

                echo "The DJ says: ${params.sTrAnGePaRaM}"
            }
        }
    }
}
