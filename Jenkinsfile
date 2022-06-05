pipeline {
    agent {
        docker {
            image 'maven:3.8.1-openjdk-8'
            args '-v $HOME/.m2:/root/.m2'
        }
    }
    stages {
        stage('git') {
            steps {
                git url: "https://github.com/angelok5200/appz_bot_example.git"
            }
        }
        stage('Build') { 
            steps {
                sh 'mvn clean install'
                sh 'mvn -e exec:java -Dexec.mainClass="kpi.acts.appz.bot.hellobot.HelloWorldBot"'
            }
        }
    }
}
