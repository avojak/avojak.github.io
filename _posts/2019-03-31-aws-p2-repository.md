---
title:  "AWS p2 Repository"
description: "AWS p2 Repository is a web application to host p2 repositories backed by AWS S3"
author: avojak
image: https://i.imgur.com/mrtGvmR.png
tags:
  - Java
  - AWS
  - p2
  - Eclipse
  - Docker
  - HTML
  - Bootstrap
  # - evergreen
---

AWS p2 Repository is a web application to host p2 repositories backed by AWS S3.

For more details about the development of AWS p2 Repository, check out my blog post.

```bash
$ docker run --rm -d -p 8081:8081 --env-file ./env.list aws-p2-repository
```

Example `env.list` file:

```properties
AWS_ACCESS_KEY_ID=FAKENOTREAL123
AWS_SECRET_KEY=FAKENOTREAL123
AWS_S3_BUCKET_NAME=p2.example.com
AWS_P2_REPO_WEBAPP_BRAND_NAME=p2.example.com
AWS_P2_REPO_WEBAPP_BRAND_ICON=https://www.example.com/icon.png
AWS_P2_REPO_WEBAPP_BRAND_FAVICON=https://www.example.com/favicon.png
AWS_P2_REPO_WEBAPP_CUSTOM_DOMAIN=p2.example.com
P2_INSPECTOR_BASE_URL=https://inspector.example.com
PORT=8081
```

GitHub Repository: [https://github.com/avojak/aws-p2-repository](https://github.com/avojak/aws-p2-repository)
Docker Hub: [https://hub.docker.com/r/avojak/aws-p2-repository](https://hub.docker.com/r/avojak/aws-p2-repository)