node(){  
	scmVars = checkout(scm)
	withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: "xl", usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
                	bat "git remote -v"
			bat "git remote set-url https://${USERNAME}:${PASSWORD}@github.com/XinFallIntern/email-test.git"       
			//bat "git config --global credential.helper wincred"
			bat returnStatus: true, script: "git branch -D db_migration"
			bat returnStatus: true, script: "git push origin :db_migration"
			bat "git checkout -b db_migration"
			bat "git push -u origin db_migration"            
	}
	
}
