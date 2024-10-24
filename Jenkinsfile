pipeline
{
	agent any
	stages
	{
		stage("contdownload")
		{
			steps
			{
				git branch: 'dev1', url: 'https://github.com/sonalirj/multibranch.git'
			}
		}
		 stage("contbuild")
                {
                        steps
                        {
                                sh 'mvn package'
                        }
                }
		 stage("contdeply")
                {
                        steps
                        {
                                deploy adapters: [tomcat9(credentialsId: '17f355db-8281-41c7-a869-ca2ec06a9844', path: '', url: 'http://172.31.11.124:8080')], contextPath: 'dev1', war: '**/*.war'
                        }
                }
	}
}
		
