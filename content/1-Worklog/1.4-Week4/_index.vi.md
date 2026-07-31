---
title: "Tuần 4"
date: 2026-06-22
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4
* Train model DenseNet121 trên SageMaker Training Job, dùng bộ data đã xử lý từ tuần trước.

### Tiến độ công việc
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Viết file `train.py` bằng Keras, dùng `argparse` để nhận hyperparameter truyền từ bên ngoài vào. | 22/06/2026 | 22/06/2026 | [TensorFlow API Docs](https://www.tensorflow.org/api_docs) |
| 3 | - Khởi tạo SageMaker TensorFlow Estimator và trỏ đường dẫn data đầu vào tới S3. | 23/06/2026 | 23/06/2026 | [SageMaker TensorFlow Estimator](https://sagemaker.readthedocs.io/en/stable/frameworks/tensorflow/sagemaker.tensorflow.html) |
| 4 | - Chạy Training Job trên máy GPU `ml.p3.2xlarge` để train cho nhanh. | 24/06/2026 | 24/06/2026 | [Amazon EC2 Instance Types](https://aws.amazon.com/ec2/instance-types/) |
| 5 | - Theo dõi tiến trình train qua CloudWatch Logs.<br>- Tiện tay fix vài lỗi đường dẫn OS lặt vặt trong container. | 25/06/2026 | 25/06/2026 | [SageMaker Training Logs](https://docs.aws.amazon.com/sagemaker/latest/dg/logging-cloudwatch.html) |
| 6 | - Kiểm tra output trên S3, xác nhận file `model.tar.gz` đã sinh ra đúng. | 26/06/2026 | 26/06/2026 | [SageMaker Model Output](https://docs.aws.amazon.com/sagemaker/latest/dg/your-algorithms-training-algo-output.html) |

### Thành tựu đạt được
* Train xong model AI đầu tiên của nhóm trên AWS. File trọng số (weights) được đóng gói đúng chuẩn SageMaker và lưu an toàn trên S3.
