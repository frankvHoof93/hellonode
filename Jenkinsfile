node {
    def app
    def registry = "frankvhoof/hellonode"
    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */

        app = docker.build("frankvhoof/hellonode")
    }
    stage('Push image') {	   7
        /* Finally, we'll push the image with two tags:	
         * First, the incremental build number from Jenkins	
         * Second, the 'latest' tag.	
         * Pushing multiple tags is cheap, as all the layers are reused. */	
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {	
            app.push("${env.BUILD_NUMBER}")	
            app.push("latest")	
        }	
    }
    stage('Remove Local Docker Image') {
     //   sh "docker image ls"
     //   sh "docker image prune -a"
                echo "Hello World!"
                bat "echo Hello from the shell"
                sh "hostname"
                sh "uptime"
    }
}
