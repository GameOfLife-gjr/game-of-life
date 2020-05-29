node('UBUNTU, AZURE')
	{
		stage('scm')
		{
			git 'https://github.com/GameOfLife-gjr/game-of-life.git'
		}
		stage('build')
		{
			sh label: '', script: 'mvn package'
		}
		
		stage('postbuild')
		{
			junit 'game-of-life\\gameoflife-web/target/surefire-reports/*.xml'
			archiveArtifacts 'gameoflife-web/target/*.war'
		}
	}
