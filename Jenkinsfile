node {

    stage('Clone Repository')
    {
        checkout scm
    }

    stage('Show me the files') 
    {
        sh "ls -l"
    }

    stage('Build docker image')
    {
	sh "docker build -t exam:latest ."
    }

    stage('Docker login to hub and push the image')
    {
	sh "docker login -u 'mopiata' -p 'dockerP@ss' "
	sh "docker tag exam:latest mopiata/exam:latest"
	sh "docker push mopiata/exam:latest"
	sh "docker run -d mopiata/exam:latest"
    }

      stage('Apply changes to the environment') 
    {
        sh "ls -l"
        sh "echo run application"
    }
}

