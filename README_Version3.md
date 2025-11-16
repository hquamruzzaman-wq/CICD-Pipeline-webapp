# cicd-node-webapp

Simple Node.js Express webapp for the AWS CI/CD pipeline app (GitHub as source).

Files:
- app.js: Express app
- package.json: Node metadata and scripts
- test.js: Simple test script
- buildspec.yml: CodeBuild spec for install/test/artifact packaging
- cicd-pipeline.yml: CloudFormation template to create S3, CodeBuild, CodePipeline (GitHub via CodeStar Connection)

Quick usage:
1. Create a GitHub repository and push these files (suggested repo name: `cicd-node-webapp`).
2. Create a CodeStar Connection in AWS Console to authorize GitHub and copy the Connection ARN.
3. Create an Elastic Beanstalk Node.js application + environment (or note existing names).
   - Suggested names:
     - Application: `cicd-webapp-app`
     - Environment: `cicd-webapp-env`
4. Deploy the CloudFormation stack (see cicd-pipeline.yml) with the GitHub owner/repo/branch and Connection ARN.
5. Push a commit to trigger the pipeline.

Local run:
- npm install
- npm start
- Open http://localhost:8080