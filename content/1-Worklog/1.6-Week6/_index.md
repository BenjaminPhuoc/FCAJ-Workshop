---
title: "Week 6"
date: 2026-07-06
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives
* Bring model artifacts under version control with SageMaker Model Registry ahead of deployment.

### Task Progress
| Day | Task | Start Date | Completion Date | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon | - Created a Model Package Group called `Pulmonary-Diagnostic-Models` in SageMaker. | 07/06/2026 | 07/06/2026 | [SageMaker Model Registry](https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry.html) |
| Tue | - Registered the top-performing model from the HPO run into the Registry via the Boto3 SDK. | 07/07/2026 | 07/07/2026 | [Boto3 ModelPackage API](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/sagemaker.html) |
| Wed | - Set up the approval workflow and marked the version `Approved`, signaling it's production-ready. | 07/08/2026 | 07/08/2026 | [MLOps Model Approval](https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-approve.html) |
| Thu | - Started building `inference.py` (the custom handler) to decode Base64 image payloads coming in from the frontend. | 07/09/2026 | 07/09/2026 | [SageMaker Inference Toolkit](https://github.com/aws/sagemaker-inference-toolkit) |
| Fri | - Ran a cross-review of the NumPy array transformations in the inference script to head off potential RAM overflow issues. | 07/10/2026 | 07/10/2026 | [NumPy Memory Management](https://numpy.org/doc/stable/user/basics.html) |

### Key Achievements
* Model lifecycle is now versioned (v1) and centrally tracked, so there's no more scattering artifacts across local folders.
