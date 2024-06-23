# trivyj-enkins
This Jenkins pipeline automates scanning multiple Docker images for vulnerabilities using Trivy. Each image is independently scanned, generating detailed reports to identify and mitigate security issues. Reports are archived for review, ensuring secure deployment. Environment variables allow scan customization.


Key Features:
Automated Vulnerability Scanning:

The pipeline iterates over a list of 40 Docker images and performs a Trivy scan for each image.
Trivy scans are configured to detect vulnerabilities of HIGH and CRITICAL severity levels.
Report Generation:

Each scan generates a report that is uniquely named based on the image name, making it easy to identify and review the results.
The reports are archived as artifacts in Jenkins for future reference and auditing.
Environment Configuration:

Docker registry URL and credentials are configured for secure access to the Docker images.
The Trivy scan severity and timeout settings are adjustable through environment variables.
Workspace Cleanup:

The pipeline ensures that the workspace is cleaned up after the execution to maintain a clean build environment.
Pipeline Stages:
Trivy Scan:

This stage iterates over the list of Docker images.
For each image, Trivy is run to scan for vulnerabilities.
The scan results are output to a text file named after the image and archived in Jenkins.
Deploy Application:

This placeholder stage is intended for deploying the application after the vulnerability scans are complete.
Deployment steps can be customized as per the project's requirements.
Post Actions:

always { cleanWs() }: Ensures that the workspace is cleaned up regardless of the build result, maintaining a tidy and manageable build environment.
Benefits:
Security: By scanning Docker images for vulnerabilities, the pipeline helps in maintaining a secure production environment.
Automation: Automating the scanning process saves time and ensures consistency in security checks.
Traceability: Each scan generates a detailed report that is archived, providing a clear audit trail for security reviews.
Flexibility: Environment variables allow easy customization of scan parameters and Docker registry configurations.
