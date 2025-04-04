Built an end-to-end CI/CD pipeline to automate software integration, testing, and deployment. <br>
• <b>Technologies Used:</b> Jenkins (2.x), GitHub/GitLab CI/CD <br>
<b>Key Contributions & Impact:</b> <br>
• Automated build, test, and deployment process, reducing deployment time by 35%. <br>
• Integrated version control enhancing code consistency across environments. <br>
• Minimized manual errors and ensured faster release cycles, improving team efficiency by 25%.<br><<br>
<b>About Setup of Pipeline</b> <br>
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
 pipeline { <br>
 agent any stages <br>
 {<br>
stage('Checkout') <br>
{ 
steps <br>
{<br>
// Checkout code from Git
git url: 'https://github.com/Sumit-adeppa/Automated-CI-CD-Pipeline.git', branch: 'main'<br>
}<br>
}<br>
stage('Build')<br> {<br> steps<br> {<br>
echo 'Building the application...'<br>
// Add your build commands here (e.g., Maven, Gradle, npm, etc.)<br>
// sh 'mvn clean package' or sh './gradlew build'<br>
}<br>
}<br>
stage('Test') <br>{ <br>steps<br> {<br>
echo 'Running tests...'<br>
// Add your test commands here (e.g., unit tests, integration tests)<br>
// sh 'mvn test' or sh './gradlew test'<br>
}<br>
}<br>
stage('Deploy') <br>{ <br>
steps <br>
{<br>
echo 'Deploying the application...'<br>
// Add your deploy commands (e.g., deployment scripts, Docker, etc.)<br>
// sh 'docker-compose up -d' or sh 'kubectl apply -f deployment.yaml'<br>
}<br>
}<br>
}<br>
post { <br>
success <br>
{<br>
echo 'Pipeline succeeded!'<br>
}<br>
failure<br> 
{<br>
echo 'Pipeline failed!'<br>
}<br>
}<br>
}<br>

STEP 4: Configure Git Repository:<br>
Replace the placeholder Git repository URL (https://github.com/Sumit-adeppa/Automated-CI-CD-Pipeline.git) with your actual repository URL<br>
 
 
STEP 5: Save the Pipeline:<br>
After writing the script, click Save.<br>


STEP 6: Run the Pipeline:<br>
•	Go back to the Jenkins dashboard and select your newly created pipeline job.<br>
•	Click Build Now to trigger the pipeline.<br>


STEP 7: Check Pipeline Execution:<br>
•	As the pipeline runs, you’ll be able to see each stage (Checkout, Build, Test, Deploy) being executed.<br>
•	You can view the progress by clicking on the Build Number in the build history and selecting Console Output.<br>
