node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */
	
	sh './dockerBuild.sh'

       /* app = docker.build("josemanuelCRV/docker-proyect") */
    }


    stage('Push image') {
        docker.withRegistry('https://hub.docker.com/', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}") 
            app.push("latest")
        }
    }
}
