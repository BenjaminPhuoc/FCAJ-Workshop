---
title: "Week 3"
date: 2026-06-15
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives
* Move the data preprocessing logic (resize, normalize) onto Amazon SageMaker Processing Jobs so it runs automatically.

### Task Progress
| Day | Task | Start Date | Completion Date | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon | - Pulled the image-processing functions out of the old Jupyter notebooks and consolidated them into a standalone `preprocessing.py` module. | 06/15/2026 | 06/15/2026 | [Scikit-image Docs](https://scikit-image.org/docs/stable/) |
| Tue | - Set up a SageMaker IAM Role with read access to the S3 bucket.<br>- Spun up SageMaker Studio to test the environment. | 06/16/2026 | 06/16/2026 | [SageMaker Execution Roles](https://docs.aws.amazon.com/sagemaker/latest/dg/sagemaker-roles.html) |
| Wed | - Wrote the SageMaker Processing Job script, configured to run on a cost-effective `ml.m5.xlarge` instance. | 06/17/2026 | 06/17/2026 | [SageMaker Python SDK](https://sagemaker.readthedocs.io/en/stable/) |
| Thu | - Kicked off the Processing Job, watched it through CloudWatch logs, and confirmed the processed dataset landed in the right S3 folder structure. | 06/18/2026 | 06/18/2026 | [Amazon CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/) |
| Fri | - Reviewed AWS Cost Explorer with the team to see what yesterday's job run cost.<br>- Sketched an outline for Blog 2. | 06/19/2026 | 06/19/2026 | [AWS Billing Console](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/) |

### Key Achievements
* Data prep now runs entirely in the cloud — SageMaker pulls, processes, and writes the dataset back to S3 in under 3 minutes.
