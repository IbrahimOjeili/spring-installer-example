node {
    stage ("clone repository") {
        git branch: 'port-9000', credentialsId: 'github', url: 'https://github.com/IbrahimOjeili/spring-boot-hello-world'
        // git "https://github.com/IbrahimOjeili/spring-boot-hello-world"
    }
    stage ("maven") {
        sh "mvn clean package"
    }
    stage ("copy jar") {
        sh "sudo cp target/hello-world-0.0.1-SNAPSHOT.jar /home/spring/app.jar"
        sh "sudo chown spring:spring /home/spring/app.jar"
    }
    stage ("restart service") {
        sh "sudo systemctl restart spring"
    }
}
