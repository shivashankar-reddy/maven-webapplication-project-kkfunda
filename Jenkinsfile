node
{
    //      /var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven-3.9.16/bin

    def mavenHome=tool name: "Maven-3.9.16"
    stage('Pipeline')
    sh 'echo "This is Scripted way pipeline 1" '

    stage('Git checkout')
    git branch: 'master', url: 'https://github.com/shivashankar-reddy/maven-webapplication-project-kkfunda.git'

    stage('Compile')
    sh "${mavenHome}/bin/mvn compile"

    stage('Build')
    sh "${mavenHome}/bin/mvn clean package"

    stage('SQ Report')
    sh "${mavenHome}/bin/mvn sonar:sonar"
    
} //Node Ending 
