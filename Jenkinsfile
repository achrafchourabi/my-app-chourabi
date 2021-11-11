pipeline
{

agent any
 stages {
  
   stage('PULL') {

   steps {
   
   script {

checkout([$class: 'GitSCM', branches: [[name: '*/master']],

userRemoteConfigs: [[

credentialsId: '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',
url: 'https://github.com/achrafchourabi/my-app-chourabi.git' ]]])



}
}
}


stage('build') {
steps{

script {

sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml "

}
}
}

stage('docker') {
steps{
script {


sh "ansible-playbook Ansible/docker.yml -i Ansible/inventory/host.yml "


}
}
}

stage('docker_registry') {
steps{
script {


sh "ansible-playbook Ansible/docker-registry.yml -i Ansible/inventory/host.yml "


}
}
}

}
}
