pipeline {
    agent any  // Utilise n'importe quel agent (machine) disponible

    stages {
        stage('Checkout') {
            steps {
                  git branch:'main', url: 'https://github.com/YoussefHalleb/HelloApp2.git'
            }
        }

        
        stage('Build') {
            steps {
               sh " docker build -t mon-node-app:latest . "
            }
        }

         stage('Login to Docker Hub') {
    		steps {
       			 echo 'Logging into Docker Hub...'
       			 withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
           		 sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
        }
    }
}

	stage('Push to Docker Hub') {
    		steps {
        		echo 'Pushing Docker image to Docker Hub...'
        		sh 'docker push youssefhalleb/mon-node-app:latest'
   			 }
		}

    }
}
 
