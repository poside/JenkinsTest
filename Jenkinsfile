pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                git branch: 'main', url: 'https://github.com/poside/JenkinsTest.git'            }
        }

        stage('OWASP DependencyCheck') {
            steps {
                dependencyCheck additionalArguments: '--format HTML --format XML --nvd-api-key 4c1b050e-c8bc-42d6-9df0-9657bd8fb182', odcInstallation: 'OWASP-Dependancy-Test'
            }
        }
    }
    post {
        success {
            dependencyCheckPublisher pattern: 'dependency-check-report.xml'
        }
    }
}
