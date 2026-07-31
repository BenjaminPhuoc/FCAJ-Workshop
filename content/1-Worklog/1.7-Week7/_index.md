---
title: "Week 7"
date: 2026-07-13
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives
* Deploy the model to a Serverless Endpoint to keep costs down.
* Build out the backend layer connecting API Gateway and AWS Lambda.

### Task Progress
| Day | Task | Start Date | Completion Date | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon | - Packaged the model archive with a `requirements.txt` (adding Pillow and numpy) so dependencies install automatically on deploy. | 07/13/2026 | 07/13/2026 | [Python PIP Packaging](https://packaging.python.org/en/latest/) |
| Tue | - Ran the deployment code to provision a SageMaker Serverless Endpoint V2 with 2GB of RAM. | 07/14/2026 | 07/14/2026 | [SageMaker Serverless Inference](https://docs.aws.amazon.com/sagemaker/latest/dg/serverless-endpoints.html) |
| Wed | - Co-wrote the AWS Lambda handler with my teammate, set the `ENDPOINT_NAME` environment variable, and assigned the IAM execution permissions. | 07/15/2026 | 07/15/2026 | [AWS Lambda Env Vars](https://docs.aws.amazon.com/lambda/latest/dg/configuration-envvars.html) |
| Thu | - Configured API Gateway to route a `POST /predict` method to the Lambda proxy. | 07/16/2026 | 07/16/2026 | [API Gateway REST APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-rest-api.html) |
| Fri | - Tested the API with cURL image payloads and confirmed valid JSON responses came back. | 07/17/2026 | 07/17/2026 | [cURL Documentation](https://curl.se/docs/) |

### Key Achievements
* Backend is fully serverless end-to-end — it scales down to zero when idle, so there's no base cost.
