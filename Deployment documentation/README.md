# Hosting a Full-Stack Application

> ## Preparing Infrastructure For Deployment

- A main configuration file is used for setting the environment variable [here](udagram/udagram-api/src/config/config.ts).
- No authentication strings are hard-coded in the source code.
- A project-level package.json file contains All the necessary scripts needed for install, build, test and deploy both the frontend and the backend.
- Screenshots of the AWS console indicate that RDS, EB and S3 are properly set up are available inside Deployment folder.
- The app is accessible via [this link](http://udagram-1.s3-website-us-east-1.amazonaws.com).

> ## Configuring Continuous Integration Pipeline with Github
- Udagram project in github repo is linked to circleci and added the `config.yml` file of the circleci containing all the orbs, jobs and workflows for running the pipeline automatically after every commit on the master branch.


 ## Pipeline Process

- `.circleci/config.yml` is added with all commands needed to complete the pipeline
- Screenshots of the circleci process is added [here](./CircleCI).

### Continuous integration:
- The scripts needed for installing, testing and building the frontend and backend of the application are found in the package.json files in `udagram-api & udagram-frontend` folders.
- The scripts are called in the project-level package.json.
- Jobs are added in the `.circleci/config.yml` file for running these scripts in the following command order:-
  - npm run frontend:install
  - npm run api:install
  - npm run frontend:build
  - npm run api:build
  - npm run frontend:test
  - npm run api:test

### Continuous Deployment:
- The scripts needed for deploying the frontend and backend of the application are found in the package.json files in `udagram-api & udagram-frontend` folders.
- The scripts are called in the project-level package.json.
- Jobs are added in the `.circleci/config.yml` file for running these scripts in the following command order:-
  - npm run frontend:deploy
  - npm run api:deploy

> ## Used Amazon Web Services
- `RDS` to create a postgreSQL database.
- `EB` to run a server and create a production Application and link it with the production environment and host the backend files.
- `S3` to create a bucket for hosting the frontend files.