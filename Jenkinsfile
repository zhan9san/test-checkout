pipeline {
    agent {
        label "${params.LABEL}"
    }
    options { timestamps () }
    parameters {
        string(name: 'LABEL', defaultValue: '', description: 'The label to test')
    }
    stages {
        stage('Hello') {
            steps {
                script {
                    if (isUnix()) {
                        sh '''
                            ps -ef | grep java
                            env | sort
                            java -version || true
                            sleep 24000
                        '''
                    } else {
                        bat '''
                            java -version
                        '''
                    }
                }
            }
        }
    }
}
