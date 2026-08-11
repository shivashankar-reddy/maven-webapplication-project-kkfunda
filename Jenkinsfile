node
{
    //      /var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven-3.9.16/bin

    def mavenHome=tool name: "Maven-3.9.16"
    
    stage('Git checkout')
    git branch: 'master', url: 'https://github.com/shivashankar-reddy/maven-webapplication-project-kkfunda.git'

    stage('Compile')
    sh "${mavenHome}/bin/mvn compile"

    stage('Build')
    sh "${mavenHome}/bin/mvn clean package"

    stage('SQ Report')
    sh "${mavenHome}/bin/mvn sonar:sonar"

    stage('Deploy Artifact to Nexus')
    sh "${mavenHome}/bin/mvn deploy"

    stage('Deploy to Tomcat')
    sh """

      curl -u kk:password \
--upload-file /var/lib/jenkins/workspace/scripted-way-PL-1/target/maven-web-application.war \
"http://13.233.139.139:8080/manager/text/deploy?path=/maven-web-application&update=true"
          
        """
    
} //Node Ending 
