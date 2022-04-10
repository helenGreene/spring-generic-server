pipeline { 
    agent any 
    stages {
        stage('checkout') { 
            steps { 
				checkout([$class: 'GitSCM', branches: [[name: '**']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'radi github token', url: 'https://github.com/DavidMilstein/simple-tests-PR.git']]])
            }
        }
        stage('collect') {
            steps {
				collectBranchesToAlmOctane configurationId: '7002083e-4ffb-491b-8e26-c3a4d0032871', credentialsId: '86098d52-2d8e-49f0-b3a8-ef60ae4c1ad5', filter: '', repositoryUrl: 'https://github.com/DavidMilstein/simple-tests-PR.git', scmTool: 'github_cloud', workspaceId: '1002'
				collectPullRequestsToAlmOctane configurationId: '7002083e-4ffb-491b-8e26-c3a4d0032871', credentialsId: '86098d52-2d8e-49f0-b3a8-ef60ae4c1ad5', repositoryUrl: 'https://github.com/DavidMilstein/simple-tests-PR.git', scmTool: 'github_cloud', sourceBranchFilter: '', targetBranchFilter: '', workspaceId: '1002'
            }
        }
    }
}
