
label = "${UUID.randomUUID().toString()}"
git_deploy_user_token = "iguazio-prod-git-user-token"
git_deploy_user_private_key = "iguazio-prod-git-user-private-key"
git_project = "ork-test"


podTemplate(label: "${git_project}-${label}", inheritFrom: "docker-python") {
    node("${git_project}-${label}") {
        pipelinex = library(identifier: 'pipelinex@development', retriever: modernSCM(
                [$class       : 'GitSCMSource',
                 credentialsId: git_deploy_user_private_key,
                 remote       : "git@github.com:iguazio/pipelinex.git"])).com.iguazio.pipelinex

        common.notify_slack {
            withCredentials([string(credentialsId: git_deploy_user_token, variable: 'GIT_TOKEN')]) {
                println("test")

            }
        }
    }
}