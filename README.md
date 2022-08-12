# Hosting a Full-Stack Application

> ## Preparing Infrastructure For Deployment

- A main configuration file is used for setting the environment variable [here](udagram/udagram-api/src/config/config.ts).
- No authentication strings are hard-coded in the source code.
- A project-level package.json file contains All the necessary scripts needed for install, build, test and deploy both the frontend and the backend.
- Screenshots of the AWS console indicate that RDS, EB and S3 are properly set up are available inside Deployment folder.
- The app is accessible via [this link](http://udagram-1.s3-website-us-east-1.amazonaws.com).

 ## Pipeline Process

- `.circleci/config.yml` is added with all commands needed to complete the pipeline
- Screenshots of the circleci process is added [here](./Deployment/CircleCI).