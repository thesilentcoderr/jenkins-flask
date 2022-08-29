pipeline{
    agent { label 'docker' }
    
    stages{
        stage('Git Fetch') {
          steps{
            dir("build_${BUILD_NUMBER}"){
                echo "git fetching"
                git branch: 'main', url: 'https://github.com/thesilentcoderr/jenkins-simlink-buildNum.git'
                echo "fetch done"
            }
          }
        }
        stage('Nginx Config') {
          steps{
            dir("build_${BUILD_NUMBER}"){
                sh 'ln -sf /home/ec2-user/workspace/dir_pipe/build_${BUILD_NUMBER}/index.html /home/ec2-user/public_html/index.html'
            }
          }
        }
        stage('Nginx Reload') {
          steps{
            dir("build_${BUILD_NUMBER}"){
                sh 'sudo nginx -s reload'
            }
          }
        }
    }
}
