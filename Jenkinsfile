pipeline{
  agent any
  stages{
    stage('fetch code from SCM'){
      steps{
        echo'successfully fetched content from SCM'
      }
    }
    
    stage('Validate contect from SCM'){
      steps{
        script{
        if (fileExists(index.html)){
          sh grep -q '</html>' index.html
          echo'validation successful'
        } else {
          error'validation failed'
        }
        }
           }
           }
           
           
    stage('deploy code to nginx'){
           sh 'cp index.html /usr/share/nginx/html'
           echo'deployment success'
    }
  }          
  }
