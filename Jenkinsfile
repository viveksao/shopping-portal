pipeline{

    agent any

// uncomment the following lines by removing /* and */ to enable
    tools{
        nodejs'nodejs'
    }
    

    stages{
        stage('build'){
            steps{
                echo 'this is the build job'
                sh 'npm compile'
            }
        }
        stage('test'){
            steps{
                echo 'this is the test job'
                sh 'npm clean test'
            }
        }
        stage('package'){
            steps{
                echo 'this is the package job'
                sh 'npm package -DskipTests'
            }
	}
       stage('Archive') {
           steps {
              archiveArtifacts '**/distribution/*.zip'
                 }
              }
        }
    }
    
    post{
        always{
            echo 'this pipeline has completed...'
        }
        
    }
    
}
