node
{
    //      /var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven-3.9.16/bin

    def mavenHome=tool name: "maven-3.9.16"
    stage('Git checkout')
    git branch: 'master', url: 'https://github.com/shivashankar-reddy/maven-webapplication-project-kkfunda.git'

    stage('Compile')
    sh "${mavenHome}/bin/mvn compile"
    
} //Node Ending 
