### BEFORE BUILDING

Add your Cesium access token to static/state.json in the accessToken field.
Deploy the AWS CloudFormation infrastructure.
Retrieve your websocket URL from the CloudFormation stack outputs.

### BUILD

```bash
npm i
AWS_SOCKET=<YOUR SOCKET URL> npm run build-client-release
```

### DEPLOY

```bash
aws s3 cp web s3://<YOUR BUCKET NAME> --recursive
```


### OPTIONAL CODEBUILD ###

Optionally, you can set up a codebuild on AWS to build this project.
The buildspec.yml is included in this repo for this purpose.
Ensure that the codebuild has the environment variable "AWS_SOCKET" filled as above.
Ensure that the codebuild references the correct bucket for the artifacts.
