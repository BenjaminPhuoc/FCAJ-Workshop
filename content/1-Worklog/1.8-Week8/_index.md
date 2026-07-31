---
title: "Week 8"
date: 2026-07-20
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives
* Set up automated email alerts for errors (monitoring).
* Stitch the standalone scripts together into one automated MLOps Pipeline.
* Write and submit Blog Post 3.

### Task Progress
| Day | Task | Start Date | Completion Date | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon | - Set up an SNS Topic and a CloudWatch Alarm watching for API Gateway 5xx errors, and confirmed the email alerts actually fire. | 07/20/2026 | 07/20/2026 | [Amazon CloudWatch & SNS](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html) |
| Tue | - Started building the MLOps Pipeline, chaining the Processing and Training scripts together. | 07/21/2026 | 07/21/2026 | [SageMaker Pipelines SDK](https://sagemaker.readthedocs.io/en/stable/amazon_sagemaker_model_building_pipeline.html) |
| Wed | - Fixed a dependency conflict by pinning `sagemaker<3.0`.<br>- Defined the DAG with `TrainingStep` and `RegisterModelStep`. | 07/22/2026 | 07/22/2026 | [PIP Dependency Management](https://pip.pypa.io/en/stable/user_guide/) |
| Thu | - Triggered a test pipeline run and watched the DAG execute automatically in the SageMaker Studio interface. | 07/23/2026 | 07/23/2026 | [SageMaker Studio UI](https://docs.aws.amazon.com/sagemaker/latest/dg/pipelines-studio.html) |
| Fri | - Wrapped up and submitted Blog Post 3, "MLOps Automation." | 07/24/2026 | 07/24/2026 | [FCAJ Blog Guidelines](https://cloudjourney.awsstudygroup.com/) |

### Key Achievements
* Put together a full end-to-end MLOps CI/CD system — retraining and registering a new model is now a single click.
* Wrapped up all 3 required technical blog posts for the program.
