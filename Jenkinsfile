@Library('ZupSharedLibs@marte') _
node {

  try {

    mvnBuildWithCompose {
      composeFileName = "docker-compose-ci.yml"
      composeService = "tech.lead"
      composeProjectName = "tech.lead"
      useBuilder = "true"
    }

    buildDockerContainerAWS {
      dockerRepositoryName = "tech.lead"
      dockerFileLocation = "."
      team = "Marte"
      dockerRegistryGroup = "Marte"
    }

  } catch (e) {

      notifyBuildStatus {
        buildStatus = "FAILED"
      }
      throw e

  }

}