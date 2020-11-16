node {
    checkout scm 

    stage("Run Python Script") {
        sh "python run.py"
    }

    stage("Trigger new build") {
        build(job: "${env.JOB_NAME}", propagate: false, wait: false)
    }
}