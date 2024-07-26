pipeline{
    agent any
    stages{
        stage("checkout git"){
            steps{
                git url: "https://github.com/Lakshya1997499/addressbook-cicd-project.git"
                echo "Addressbook repo cloned"
            }
        }
        stage("compile the code"){
            steps{
                echo "compiling starting"
                sh "mvn compile"
                echo "compiling done"
            }
        }
        stage("Testing of the code"){
            steps{
                echo "testing steps"
                sh "mvn test"
            }
        }
        stage("qa of the code"){
            steps{
                sh "mvn pmd:pmd"
            }
        }
        stage("package"){
            steps{
                sh "mvn package"
            }
        }
        stage("deployment of the app"){
            steps{
                sh "sudo mv /var/lib/jenkins/workspace/addressbook_deployment/target/addressbook.war /home/ubuntu/apache-tomcat-9.0.91/webapps"
            }
        }


    }
    
}
