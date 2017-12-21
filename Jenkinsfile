node {
  def appName = 'gerua'
  def feSvcName = "${appName}-frontend"
  def imageTag = "${appName}:${env.BRANCH_NAME}.${env.BUILD_NUMBER}"

  checkout scm

  stage 'Build image'
  sh("echo `imageTag is ${imageTag}`")

  stage "Deploy Application"
  switch (env.BRANCH_NAME) {
    // Roll out to canary environment
    case "canary":
        // Change deployed image in canary to the one we just built
        sh("echo `feSvcName is ${feSvcName}`")
        break

    // Roll out to production
    case "master":
        // Change deployed image in canary to the one we just built
	sh("echo `feSvcName is ${feSvcName}`")
        break
  }
}
