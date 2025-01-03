node {
    stage('Download code from git repo') {
    git branch: 'dev', url: 'https://github.com/clouddevopseng/nep.git'
                                         }
    stage('Convert into artifacts') {
    sh 'mvn package'
                                         }
    stage('Deploy into Container') {
    deploy adapters: [tomcat9(credentialsId: 'dev-ENV', path: '', url: 'http://172.31.1.31:8080')], contextPath: '/scripting-app', war: '**/*.war'
                                         }
}
