node(){  
	scmVars = checkout(scm)
	withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: "xl", usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {
			bat "git diff origin/master --name-status > diff.txt"
			bat "cat diff.txt"
			//bat "git config --global credential.helper wincred"
			bat returnStatus: true, script: "git branch -D db_migration "
			bat returnStatus: true, script: "git push https://${USERNAME}:${PASSWORD}@github.com/XinLian97/test.git :db_migration"
			bat "git checkout -b db_migration"
			bat "git push https://${USERNAME}:${PASSWORD}@github.com/XinLian97/test.git db_migration"            
	}
	
}
