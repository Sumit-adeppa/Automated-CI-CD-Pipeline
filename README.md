Jenkins Job Creation: Implementing Version Control in Your CI/CD Pipeline

Step 1: Access Jenkins
1.	Open your web browser and navigate to your Jenkins server (e.g., `http://localhost:8080`).
2.	Log in with your credentials.













STEP 2: Create a Pipeline Job:
1.	In Jenkins, click on New Item in the Jenkins dashboard.
2.	Enter a name for your job, select Pipeline as the project type, and click OK.
 
 



3.	Under the Pipeline section, choose Pipeline script.



STEP 3: Write the Jenkins Pipeline Script:
You can write a simple declarative pipeline that showcases multiple stages like build, test, and deploy.
Here’s a basic example of a Jenkins pipeline script:
 
pipeline { agent any stages {
stage('Checkout') { steps {
// Checkout code from Git
git url: 'https://github.com/Sumit-adeppa/Library.git', branch: 'main'
}
}
stage('Build') { steps {
echo 'Building the application...'
// Add your build commands here (e.g., Maven, Gradle, npm, etc.)
// sh 'mvn clean package' or sh './gradlew build'
}
}
stage('Test') { steps {
echo 'Running tests...'
// Add your test commands here (e.g., unit tests, integration tests)
// sh 'mvn test' or sh './gradlew test'
}
}
stage('Deploy') { steps {
echo 'Deploying the application...'
// Add your deploy commands (e.g., deployment scripts, Docker, etc.)
// sh 'docker-compose up -d' or sh 'kubectl apply -f deployment.yaml'
}
 
}
}
post { success {
echo 'Pipeline succeeded!'
}
failure {
echo 'Pipeline failed!'
}
}
}











STEP 4: Configure Git Repository:
Replace the placeholder Git repository URL (https://github.com/Sumit-adeppa/Library.git) with your actual repository URL
 
 







STEP 5: Save the Pipeline:
After writing the script, click Save.


STEP 6: Run the Pipeline:
•	Go back to the Jenkins dashboard and select your newly created pipeline job.
•	Click Build Now to trigger the pipeline.


STEP 7: Check Pipeline Execution:
•	As the pipeline runs, you’ll be able to see each stage (Checkout, Build, Test, Deploy) being executed.
•	You can view the progress by clicking on the Build Number in the build history and selecting Console Output.
 
 


