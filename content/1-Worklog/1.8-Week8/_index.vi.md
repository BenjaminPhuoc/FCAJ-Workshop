---
title: "Tuần 8"
date: 2026-07-20
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8
* Setup cảnh báo lỗi tự động qua Email (Monitoring).
* Gộp các script rời rạc thành một MLOps Pipeline tự động.
* Viết và nộp bài Blog số 3.

### Tiến độ công việc
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tạo SNS Topic và CloudWatch Alarm theo dõi lỗi 5xx của API Gateway, test gửi cảnh báo qua email thành công. | 20/07/2026 | 20/07/2026 | [Amazon CloudWatch & SNS](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html) |
| 3 | - Bắt đầu xây Pipeline, nối mã nguồn Processing và Training lại với nhau. | 21/07/2026 | 21/07/2026 | [SageMaker Pipelines SDK](https://sagemaker.readthedocs.io/en/stable/amazon_sagemaker_model_building_pipeline.html) |
| 4 | - Xử lý lỗi đụng độ thư viện bằng cách ghim version `sagemaker<3.0`.<br>- Định nghĩa DAG gồm `TrainingStep` và `RegisterModelStep`. | 22/07/2026 | 22/07/2026 | [PIP Dependency Management](https://pip.pypa.io/en/stable/user_guide/) |
| 5 | - Chạy thử Pipeline và theo dõi luồng DAG tự động chạy trên giao diện SageMaker Studio. | 23/07/2026 | 23/07/2026 | [SageMaker Studio UI](https://docs.aws.amazon.com/sagemaker/latest/dg/pipelines-studio.html) |
| 6 | - Cùng nhóm hoàn thiện và nộp bài Blog số 3 "Tự động hóa MLOps". | 24/07/2026 | 24/07/2026 | [Quy định FCAJ Blog](https://cloudjourney.awsstudygroup.com/) |

### Thành tựu đạt được
* Đóng gói xong hệ thống MLOps CI/CD end-to-end — chỉ cần 1 click là tự động train và đăng ký model mới.
* Hoàn thành đủ 3 bài Blog công nghệ theo yêu cầu chương trình.
