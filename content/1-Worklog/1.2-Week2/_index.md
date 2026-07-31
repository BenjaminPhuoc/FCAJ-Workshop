---
title: "Week 2"
date: 2026-06-08
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives
* Build a lightweight Toy Dataset for experimental training runs to keep AWS costs down.
* Draft, finalize, and submit the first technical blog post.

### Task Progress
| Day | Task | Start Date | Completion Date | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon | - Locked in the architecture with the team: moving fully to Serverless (API Gateway + Lambda + SageMaker) to cut operating costs. | 06/08/2026 | 06/08/2026 | [AWS Serverless Architecture](https://aws.amazon.com/serverless/) |
| Tue | - Took on writing `create_toy_dataset.py`, a script that randomly samples 120 class-balanced chest X-ray images. | 06/09/2026 | 06/09/2026 | [Python Pandas Docs](https://pandas.pydata.org/docs/) |
| Wed | - Ran the splitting script and double-checked the Train/Val folder structure.<br>- Teammate provisioned the Amazon S3 bucket in parallel. | 06/10/2026 | 06/10/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/) |
| Thu | - Synced the finished Toy Dataset up to the project's S3 bucket via AWS CLI. | 06/11/2026 | 06/11/2026 | [AWS CLI S3 Commands](https://docs.aws.amazon.com/cli/latest/reference/s3/) |
| Fri | - Worked together on drafting and formatting Blog 1, "Serverless MLOps Architecture," ahead of submission. | 06/12/2026 | 06/12/2026 | [FCAJ Blog Guidelines](https://cloudjourney.awsstudygroup.com/) |

### Key Achievements
* Got a downsized dataset live on S3 — later code tests now finish in 1–2 minutes, keeping us within FinOps guidelines.
* Blog Post 1 submitted on time.
