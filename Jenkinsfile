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

}
}
