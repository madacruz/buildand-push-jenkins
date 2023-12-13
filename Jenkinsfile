node {

   def registryProjet='forma-mathilde/'
   def IMAGE="${registryProjet}app:3.2"

    stage('Clone') {
          checkout scm
    }

    def img = stage('Build') {
          docker.build("$IMAGE",  '.')
          }

    stage('Run') {
          img.withRun("--name run-$BUILD_ID") { c ->
       
          }
    }

    stage('Push') {
       docker.withRegistry('https://registry.ludovic.io/' , 'mdacruz') {
              img.push 'latest'
              img.push()
          }
    }

}

