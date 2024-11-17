pipeline {
    agent any  // Utilise n'importe quel agent (machine) disponible

    stages {
        stage('Checkout') {
            steps {
                    git 'https://github.com/YoussefHalleb/HelloNodeApp.git'
            }
        }

        
        stage('Build') {
            steps {
               sh " docker build -t mon-node-app:latest . "
            }
        }

        // Stage 3: Deploy
        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying the application...'
                    // Ajoutez ici vos commandes pour déployer l'application
                    // Par exemple : sh 'docker-compose up' ou des scripts de déploiement
                }
            }
        }
    }

 
