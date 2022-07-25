pipeline{
    agent { label 'prod' }
    
    stages{
        stage('Git Fetch') {
          steps{
            dir("build_${BUILD_NUMBER}"){
                echo "git fetching"
                git branch: 'main', url: 'https://github.com/thesilentcoderr/jenkins-flask.git'
                echo "fetch done"
            }
          }
        }
        stage('Nginx Config') {
          steps{
            dir("build_${BUILD_NUMBER}"){
                sh 'ln -sf /home/ec2-user/build_symlink/index.html /home/ec2-user/public_html/index.html'
            }
          }
        }
    }
}