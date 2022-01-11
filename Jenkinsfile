pipeline{
     agent {
    docker {
        image 'gaddamnarendra/myprivaterepo:latest'
        //label 'latest'
        //repository/docker/gaddamnarendra/myprivaterepo https://hub.docker.com/
        registryUrl 'https://registry.hub.docker.com'
        registryCredentialsId 'DOCKER_CRDS'
    }
}
      stages{
           /*stage('Pull image'){
              steps{
                    script{
                         docker.withRegistry('https://registry.hub.docker.com','DOCKER_CRDS')
                            {
                              def image=docker.image('gaddamnarendra/myprivaterepo:latest')
                              image.pull()
                             }
                          }
                     }
               }*/
        stage('SCM checkout')
        {
            steps{
            git 'https://github.com/PoojyaShree/maven-web-application'
            }
        }
        stage('maven Build') {
            steps {
                sh 'mvn -B clean package'
            }
        }
      }
}
