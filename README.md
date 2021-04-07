# aws-cli-action

### Purpose
Use this Github Action if you have anything to do with AWS using AWS CLI in your CI/CD. It can be as simple as creating a file to push it to S3 bucket or it can get as complex as creating AWS related resources like EC2, IAM, SG, etc..

### How does it do it?
It internally uses AWS (officially) supported AWS-CLI container to trigger the action.

### Sample Usage

> Note: You can do whatever you can do with the AWS CLI in this github action. As mentioned, it internally the AWS-CLI container to do the action. No custom scripting. No incompatability issues. No issues!!! (unless AWS CLI itself has bugs)


```
jobs:
  deploy-prod:
    runs-on: ubuntu-latest

    steps:
      - name: s3 sync
        id: s3-sync
        uses: envoy/aws-cli-action@main
        with:
          args: s3 sync . s3://<bucket-name> --acl private
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          AWS_DEFAULT_REGION: ${{ secrets.AWS_DEFAULT_REGION }}
```
