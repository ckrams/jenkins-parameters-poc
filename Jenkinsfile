pipeline {
    agent any
    parameters {
        string(name: 'STRING_PARAM', defaultValue: 'default_value', description: 'A simple string parameter')
        booleanParam(name: 'BOOLEAN_PARAM', defaultValue: true, description: 'A boolean parameter (checkbox)')
        choice(name: 'CHOICE_PARAM', choices: ['Option A', 'Option B', 'Option C'], description: 'A choice parameter with predefined options')
        text(name: 'TEXT_AREA_PARAM', defaultValue: 'Multi-line\ntext\nexample', description: 'A multi-line text area parameter')
        password(name: 'PASSWORD_PARAM', defaultValue: 'secret', description: 'A password parameter (masked input)')
    }
    stages {
        stage('Process Parameters') {
            steps {
                script {
                    echo "String Parameter: ${params.STRING_PARAM}"
                    echo "Boolean Parameter: ${params.BOOLEAN_PARAM}"
                    echo "Choice Parameter: ${params.CHOICE_PARAM}"
                    echo "Text Area Parameter:\n${params.TEXT_AREA_PARAM}"
                    // Note: Password parameters are typically not echoed directly for security reasons.
                    // Accessing them should be done carefully, for example, when passing to a secure credential.
                    echo "Password Parameter (for demonstration, normally not echoed): ${params.PASSWORD_PARAM}"
                }
            }
        }
        stage('Conditional Execution') {
            when {
                expression { params.BOOLEAN_PARAM == true }
            }
            steps {
                echo "This stage runs because BOOLEAN_PARAM is true."
            }
        }
    }
}
