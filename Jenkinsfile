node(){  
	scmVars = checkout(scm)
	withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: "xl", usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
			       
			//bat "git config --global credential.helper wincred"
			bat returnStatus: true, script: "git https://${USERNAME}:${PASSWORD}@github.com/XinLian97/test.git branch -D db_migration"
			bat returnStatus: true, script: "git https://${USERNAME}:${PASSWORD}@github.com/XinLian97/test.git push origin :db_migration"
			bat "git push https://${USERNAME}:${PASSWORD}@github.com/XinLian97/test.git"
			bat "git checkout -b db_migration"
			bat "git push -u origin db_migration"            
	}
	
}
