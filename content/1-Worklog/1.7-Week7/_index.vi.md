---
title: "Tuần 7"
date: 2026-07-13
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7
* Deploy model lên Serverless Endpoint để tiết kiệm chi phí.
* Dựng tầng Backend kết nối API Gateway và Lambda.

### Tiến độ công việc
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Đóng gói model kèm `requirements.txt` (thêm Pillow, numpy) để lúc deploy tự cài đủ thư viện. | 13/07/2026 | 13/07/2026 | [Python PIP Packaging](https://packaging.python.org/en/latest/) |
| 3 | - Chạy code deploy để dựng SageMaker Serverless Endpoint V2, cấu hình 2GB RAM. | 14/07/2026 | 14/07/2026 | [SageMaker Serverless Inference](https://docs.aws.amazon.com/sagemaker/latest/dg/serverless-endpoints.html) |
| 4 | - Cùng nhóm code hàm AWS Lambda; mình phụ trách gắn biến môi trường `ENDPOINT_NAME` và cấp quyền IAM Role. | 15/07/2026 | 15/07/2026 | [AWS Lambda Env Vars](https://docs.aws.amazon.com/lambda/latest/dg/configuration-envvars.html) |
| 5 | - Cấu hình API Gateway, map method `POST /predict` tới Lambda proxy. | 16/07/2026 | 16/07/2026 | [API Gateway REST APIs](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-rest-api.html) |
| 6 | - Dùng cURL bắn ảnh test vào API, kết quả trả về JSON đúng như mong đợi. | 17/07/2026 | 17/07/2026 | [cURL Documentation](https://curl.se/docs/) |

### Thành tựu đạt được
* Backend Serverless đã hoàn chỉnh — không có request thì hạ tài nguyên về 0, hóa đơn AWS = $0.00.
