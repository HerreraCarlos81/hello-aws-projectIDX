# Project IDX + Svelte + AWS

This project demonstrates how to create a Svelte web app using Project IDX IDE templates and deploy it as a static website using AWS S3.

## Prerequisites

- AWS CLI
- Svelte
- Project IDX IDE

## Steps

1. **Prepare AWS Account**

The account preparation is a standard one as we are only going to need two services: S3 and IAM. 

- Create an AWS account following this link: [AWS Sign up](https://portal.aws.amazon.com/billing/signup#/start/email)
- Configure an IAM user using this guide:    [AWS IAM User for CLI](https://codedneurons.com/aws_iam_user_for_cli.pdf)
- Configure the permissions for the user:    [AWS IAM S3 Permissions](https://codedneurons.com/aws_iam_s3_permissions.pdf)

Now you are all set to start using the CLI on project IDX

2. **Access and start Project IDX**

- Access project IDX at [idx.google.com](https://idx.google.com/)
- In case you still don't have access, request at [idx.dev](https://idx.dev/)

- Select the "See all templates ->" link or click [here](https://idx.google.com/templates) to go directly to the templates page.
- Choose the Svelte template and wait for Project IDX to build the virtual environment, it should take about 2 minutes.

3. **Configure AWS CLI**

- Use the previously generated AWS IAM user Access Key to configure the AWS CLI
```bash
aws configure
```
- Select aws_cli2 when prompted for which AWS CLI to use.

2. **Create S3 Bucket**

```bash
aws s3 mb s3://your-bucket-name
```

3. **Enable Static Hosting**

```bash
aws s3 website s3://your-bucket-name --index-document index.html
```

4. **Build Svelte App**

```bash
npm run build
```

5. **Upload Compiled App to S3 Bucket**

```bash
aws s3 cp ./dist s3://your-bucket-name --recursive
```

## Accessing Your Website

Your website will be accessible at the following URL:

```
http://[your-bucket-name].s3-website.[region].amazonaws.com
```


```js
// store.js
// An extremely simple external store
import { writable } from 'svelte/store'
export default writable(0)
```
