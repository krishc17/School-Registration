node{
  stage ('Build') {
     git url: 'https://github.com/krishc17/maven-samples.git'
     withMaven(
        maven: 'maven_1',
        mavenSettingsConfig: 'c4128ab8-6b67-435e-b536-b4ed8e8fb5fb') {
        sh "mvn clean package"
 
    } 
  }
  stage ("Deploy"){
sh "sudo docker run -d -p 81:8080 --name mytomcat tomcat"
sh "sudo docker cp /var/lib/jenkins/workspace/cicd_pipeline/multi-module/webapp/target/webapp.war mytomcat:/usr/local/tomcat/webapps/"
}
}
