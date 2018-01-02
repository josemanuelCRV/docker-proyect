node {
    checkout scm

    docker.withRegistry('https://hub.docker.com/', 'docker-hub-credentials') {

        def customImage = docker.build("docker-proyect:${env.BUILD_ID}")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
