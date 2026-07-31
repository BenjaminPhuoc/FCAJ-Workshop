---
title: "Week 5"
date: 2026-06-29
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives
* Run Hyperparameter Optimization (HPO) so the model finds its own best parameters.
* Finish and submit Blog Post 2.

### Task Progress
| Day | Task | Start Date | Completion Date | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon | - Set the HPO search space: learning rate between `1e-5` and `1e-2`, batch size of 16 or 32. | 06/29/2026 | 06/29/2026 | [SageMaker HPO Guide](https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning.html) |
| Tue | - Configured the `HyperparameterTuner`, with Recall as the objective metric to maximize. | 06/30/2026 | 06/30/2026 | [Boto3 HyperparameterTuner API](https://sagemaker.readthedocs.io/en/stable/api/training/tuner.html) |
| Wed | - Launched the HPO job with up to 3 parallel runs to cut down wait time. | 07/01/2026 | 07/01/2026 | [AWS Tuning Best Practices](https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning-considerations.html) |
| Thu | - Once the HPO job wrapped, compared the results in SageMaker Studio's charts and picked the model with the best Recall score. | 07/02/2026 | 07/02/2026 | [SageMaker Studio Analytics](https://docs.aws.amazon.com/sagemaker/latest/dg/studio-analyze.html) |
| Fri | - Finished writing Blog Post 2 and submitted it. | 07/03/2026 | 07/03/2026 | [FCAJ Blog Guidelines](https://cloudjourney.awsstudygroup.com/) |

### Key Achievements
* Landed on the best hyperparameter configuration systematically, without hand-editing code between runs.
* Blog Post 2 published successfully.
