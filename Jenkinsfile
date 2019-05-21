node{
    stage("克隆"){
        git 'http://29.212.67.89:5001/root/myhello.git'
    }
    stage("编译打包"){
        def MvnHome = tool name: 'maven', type: 'maven'
        def MvnCMD = "${MvnHome}/bin/mvn"
        sh "${MvnCMD} clean package"
    }
    stage("制作Docker镜像"){
        sh 'docker build  -t h1docker/appdemon:v1 .'
    }
    stage("推送镜像"){
        withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubPwd')]) {
         // some block
         sh "docker login -u h1docker -p ${dockerHubPwd}"
         sh 'docker push h1docker/appdemon:v1'
        }
        
    }
    // stage("运行镜像"){
    //     sh 'docker run -d --name=appdemon appdemon:v1'
    // }
}
