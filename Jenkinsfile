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
stage('build')
steps{

script {

sh "Ansible-playbook ansible/build.yml -i Ansible/inventory/host.yml "

}
}

}
}
