pipeline{
    agent any;
    stages{
        stage("code clone") {
            steps{
                git url:"https://github.com/Adarshrajput0770/online_shopping_app.git",branch:"master"
            }
        }
        stage("trivy fs scan") {
            steps{
                sh "trivy fs ."
            }
        }
        stage("code build") {
            steps{
                sh "docker build -t online-shop ."
            }
        }
        stage("trivy image scan") {
            steps{
                sh "trivy image online-shop:latest"
            }
        }
         stage("Push to DockerHub") {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: "dockerhubcred",
                    usernameVariable: "USER",
                    passwordVariable: "PASS"
                )]) {
                    sh "echo $PASS | docker login -u $USER --password-stdin"
                    sh "docker image tag online-shop $USER/online-shop"
                    sh "docker push $USER/online-shop:latest"
                }
            }
        }
        stage("Deploy k8s"){
            steps{
                sh "kubectl apply -f kubernetes/deployment.yml"
                sh "kubectl apply -f kubernetes/service.yml"
            }
        }
    }
    
}
