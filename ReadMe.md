# New Relic Amazon Connect Monitoring Deployment Guide

## Deploying the app

### CCP URL

This parameter is the URL you use to access the Contact Control Panel. For example, if your instance is named 'monitoring-test' it would be https://monitoring-test.awsapps.com/connect/ccp-v2

### SAML URL

If you use SAML to authenticate users, enter your SAML URL. If not, leave this field blank.

Then click deploy! For a guide with pictures please follow the link to our [GitHub Repo](https://github.com/haihongren/amazon-connect-call-quality-monitoring)

### New Relic

- New Relic Firehose Endpoint: https://aws-api.newrelic.com/firehose/v1
- NewRelicKey: New Relic Insight insert API key
## Post-Deploy Steps

### Whitelisting your CloudFront URL

The custom, metrics-enabled softphone is hosted on Cloudfront. To access the custom CCP, you need to whitelist the CloudFront URL from your Connect instance. You can do this from the AWS Console for Connect.

 From the console where you found your Connect Instance ID

- Click Application Integration on the left hand side
- Click 'Add Origin'
- Find CloudFront URL from the CloudFormation stack serverlessrepo-NewRelicAmazonConnectMonitoringSolution `Outputs` 
- Paste the value

### Import New Relic Dashboard 

- Login to New Relic https://one.newrelic.com/

- Import dashboard  (replace accountId in the json with your New Relic Account Id)

    https://github.com/haihongren/amazon-connect-call-quality-monitoring/tree/master/dashboard

