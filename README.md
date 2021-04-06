# aws-cli-action

### Usage

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
