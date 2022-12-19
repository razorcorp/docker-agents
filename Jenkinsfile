pipeline {
    agent {
        docker 'jenkins/inbound-agent:alpine'
    }

    options {
        timestamps()
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }

    stages {
        stage('Build Go Agent') {
            steps {
                dir('inbound-agent-go') {
                    sh"""
                        docker build -t registry.razorcorp.dev/inbound-agent-go:lts .
                        docker push registry.razorcorp.dev/inbound-agent-go:lts
                    """
                }
            }
        }

        stage('Build Node Agent') {
            steps {
                dir('inbound-agent-node-12') {
                    sh"""
                        docker build -t registry.razorcorp.dev/inbound-agent-node-12:lts .
                        docker push registry.razorcorp.dev/inbound-agent-node-12:lts
                    """
                }
            }
        }
    }

    // TODO: Add post action Slack alerts
    //post {
    //    success {
    //    }

    //    failure {
    //    }
    //}
}
