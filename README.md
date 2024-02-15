# Project IDX + Svelte + AWS

# Project IDX + Svelte + AWS

This project demonstrates how to create a Svelte webapp using Project IDX IDE and deploy it as a static website using AWS S3.

## Prerequisites

- AWS CLI
- Svelte
- Project IDX IDE

## Steps

1. **Configure AWS CLI**

```bash
aws configure
```

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
