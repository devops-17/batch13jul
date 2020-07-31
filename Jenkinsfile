pipeline
{
	agent any
	stages
	{
		stage('Checkout')
		{
			steps
			{
				git 'https://github.com/iamdevopstrainer/DevOpsClassCodes'
			}
		}
		
		stage('Compile')
		{
			steps
			{
				sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn compile'
			}
		}

		stage('Test')
		{
			steps
			{
				sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn test'
			}
		}

		stage('Build')
		{
			steps
			{
				sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/myMaven/bin/mvn package'
			}
		}
		
		stage('Deployment
		{
			steps
			{
				echo "Deployment"
				sh 'sudo cp /var/lib/jenkins/workspace/AddressBookPipeline/target/addressbook.war /usr/share/tomcat/webapps/'
				sh 'sudo systemctl stop tomcat'
				sh 'sudo rm -rf /usr/share/tomcat/webapps/addressbook'
				sh 'sudo systemctl start tomcat'
			}
		}
     }
}
