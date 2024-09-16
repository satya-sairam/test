pipeline {
    agent any

    parameters {
        string(name: 'EZFAB_URL', defaultValue: 'http://example.com/ezfab', description: 'URL for EZFAB')
        string(name: 'REGISTRY_URL', defaultValue: 'http://example.com/registry', description: 'Registry URL')
        string(name: 'HTTP_PROXY', defaultValue: 'http://proxy.example.com:80', description: 'HTTP Proxy')
        string(name: 'COORDINATOR_IPS', defaultValue: '10.227.215.129', description: 'Coordinator IPs')
        string(name: 'WORKER_IPS', defaultValue: '10.227.215.131 10.227.211.28 10.227.211.29', description: 'Worker IPs')
    }

    stages {
        stage('Update Variables') {
            steps {
                script {
                    withEnv([
                        "EZFAB_URL=${params.EZFAB_URL}",
                        "REGISTRY_URL=${params.REGISTRY_URL}",
                        "HTTP_PROXY=${params.HTTP_PROXY}",
                        "COORDINATOR_IPS=${params.COORDINATOR_IPS}",
                        "WORKER_IPS=${params.WORKER_IPS}"
                    ]) {
                        sh './update_vars.sh'
                    }
                }
            }
        }
    }
}
