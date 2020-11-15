node {
    checkout scm 
    
    stage("Run Python Script") {
        sh "python run.py"
    }

    stage("Trigger new build") {
        build "${env.JOB_NAME}"
    }
}