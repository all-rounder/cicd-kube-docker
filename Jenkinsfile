pipeline {

    agent any
/*
	tools {
        maven "maven3"
    }
*/
    environment {
		registry = "xiaoyao160/vproappdock"
		registryCredential = 'dockerhub'
    }

    stages{
        stage('Kubernetes Deploy') {
            agent {label 'KOPS'}
                steps {
                  sh "sudo helm upgrade --install --force vprofile-stack helm/vprofilecharts --set appimage=${registry}:V11 --namespace prod"
                }
        }

    }

}
