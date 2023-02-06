pipeline {
    agent any

    stages {
        stage("Checkout Code") {
            steps {
                git url: "https://github.com/your-repo/k8s-manifests.git"
            }
        }

        stage("Deploy to Kubernetes") {
            steps {
                withKubernetes([
                    credentialsId: "my-k8s-credentials",
                    clusterName: "my-eks-cluster"
                ]) {
                    sh "kubectl apply -f ingress.yaml"
                    sh "kubectl apply -f service.yaml"
                }
            }
        }
    }
}
