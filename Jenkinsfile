pipeline {
    agent any
    options { skipDefaultCheckout() }
    stages {
        stage('Build') {
            steps {
                checkout([$class: 'GitSCM',
                    userRemoteConfigs: scm.userRemoteConfigs,
                    branches: scm.branches,
                    extensions: [authorInChangelog()]
                ])
                echo "Building ${env.GIT_COMMIT}"
            }
        }
    }
}