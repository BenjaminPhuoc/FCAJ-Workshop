---
title: "Tuần 6"
date: 2026-07-06
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6
* Đưa model vào quản lý phiên bản bằng SageMaker Model Registry trước khi deploy.

### Tiến độ công việc
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tạo Model Package Group tên `Pulmonary-Diagnostic-Models` trên SageMaker. | 06/07/2026 | 06/07/2026 | [SageMaker Model Registry](https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry.html) |
| 3 | - Dùng boto3 register model tốt nhất từ đợt HPO tuần trước vào Registry. | 07/07/2026 | 07/07/2026 | [Boto3 ModelPackage API](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/sagemaker.html) |
| 4 | - Thiết lập quy trình duyệt, chuyển status của version này sang `Approved` để báo hiệu sẵn sàng lên Production. | 08/07/2026 | 08/07/2026 | [MLOps Model Approval](https://docs.aws.amazon.com/sagemaker/latest/dg/model-registry-approve.html) |
| 5 | - Bắt đầu viết `inference.py` (Custom Handler) để giải mã ảnh Base64 gửi xuống từ Frontend. | 09/07/2026 | 09/07/2026 | [SageMaker Inference Toolkit](https://github.com/aws/sagemaker-inference-toolkit) |
| 6 | - Review chéo đoạn code xử lý array numpy trong inference để tránh lỗi tràn RAM. | 10/07/2026 | 10/07/2026 | [NumPy Memory Management](https://numpy.org/doc/stable/user/basics.html) |

### Thành tựu đạt được
* Model giờ đã có version (v1) và được quản lý tập trung, không còn lưu file rải rác trong ổ cứng nữa.
