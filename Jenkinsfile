node {
    def app

    stage('Clone repository') {
        /* Clone repository to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image */

        app = docker.build("felilca/ubuntu:latest")
    }
    
    stage ('Aqua Scan') {
        aqua customFlags: '', hideBase: false, hostedImage: '', localImage: 'felilca/ubuntu:latest', locationType: 'local', notCompliesCmd: '', onDisallowed: 'fail', policies: '', register: false, registry: '', showNegligible: false
    }
    
    /*stage('Push image') {*/
        /* Finally, we'll push the image with two tags:
         * First, the incremental build number from Jenkins
         * Second, the 'latest' tag.
         */
        /*docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }*/
}
