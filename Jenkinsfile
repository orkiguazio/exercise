node {
    checkout scm 
    
    stage("install python req") {
        pip install -r requirements.txt
    }
    stage("Run Python Script") {
        sh "python run.py"
    }

    stage("Trigger new build") {
        build(job: "${env.JOB_NAME}", propagate: false, wait: false)
    }
}