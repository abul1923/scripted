node {   
    def remote = [:]
    remote.name = "linux"
    remote.host = "dodonotdo.in"
    remote.allowAnyHosts = true

    stage('Checkout the dockefile from GitHub') {            
      git branch: 'mycodes', url: 'https://github.com/abul1923/scripted.git'        
    }
     
    stage('Build the Kubernetes YAML Files for New App') {
    withCredentials([usernamePassword(credentialsId: 'sshUserAcct', passwordVariable: 'password', usernameVariable: 'userName')]) {
        remote.user = userName
        remote.password = password
        stage("Depolyment") {
            sshCommand remote: remote, command: 'ls'

        }
    }  
    } 
}
