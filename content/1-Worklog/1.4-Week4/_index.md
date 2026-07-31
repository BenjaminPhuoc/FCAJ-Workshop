---
title: "Week 4"
date: 2026-06-22
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives
* Train the DenseNet121 model on SageMaker using last week's preprocessed dataset.

### Task Progress
| Day | Task | Start Date | Completion Date | Reference Sources |
| --- | --- | --- | --- | --- |
| Mon | - Wrote the Keras `train.py` script with `argparse` so hyperparameters can be passed in externally. | 06/22/2026 | 06/22/2026 | [TensorFlow API Docs](https://www.tensorflow.org/api_docs) |
| Tue | - Set up the SageMaker TensorFlow Estimator and wired up the S3 input data channels. | 06/23/2026 | 06/23/2026 | [SageMaker TensorFlow Estimator](https://sagemaker.readthedocs.io/en/stable/frameworks/tensorflow/sagemaker.tensorflow.html) |
| Wed | - Kicked off the Training Job on a GPU-backed `ml.p3.2xlarge` instance to speed things up. | 06/24/2026 | 06/24/2026 | [Amazon EC2 Instance Types](https://aws.amazon.com/ec2/instance-types/) |
| Thu | - Tracked training progress in CloudWatch Logs.<br>- Cleaned up a couple of minor file-path bugs inside the container. | 06/25/2026 | 06/25/2026 | [SageMaker Training Logs](https://docs.aws.amazon.com/sagemaker/latest/dg/logging-cloudwatch.html) |
| Fri | - Checked the output artifacts on S3 and confirmed `model.tar.gz` was generated correctly. | 06/26/2026 | 06/26/2026 | [SageMaker Model Output](https://docs.aws.amazon.com/sagemaker/latest/dg/your-algorithms-training-algo-output.html) |

### Key Achievements
* Got the team's first model trained end-to-end on AWS, with the weights packaged to SageMaker standards and safely stored in S3.
