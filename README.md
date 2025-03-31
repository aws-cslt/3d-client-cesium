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
