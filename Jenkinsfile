node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }

    stage('Build image') {
	    
       sh('docker build -t codagott/node-app:2.0 .')
    }

    stage('Login into Docker Hub') {
	    
        sh('docker login -u codagott -p mP3UzdZ8v7cqgEZ')
    }

    stage('Push image') {
        /* 
			You would need to first register with DockerHub before you can push images to your account
		*/
//         docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
//             app.push("${env.BUILD_NUMBER}")
//             app.push("latest")
//             } 
//                 echo "Trying to Push Docker Build to DockerHub"
	    sh('docker push codagott/node-app:2.0')
    }
	
    stage('Deploy Node-app Container ') {
	    
        sh('docker run -d -p 8070:8000 88337744666/node-app:2.0')
    }

}
