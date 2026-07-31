---
title: "Tuần 3"
date: 2026-06-15
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3
* Đưa toàn bộ bước tiền xử lý dữ liệu (resize, normalize) lên chạy tự động bằng Amazon SageMaker Processing Job.

### Tiến độ công việc
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tách các hàm xử lý ảnh ra khỏi mấy file Jupyter Notebook cũ, gom vào một file `preprocessing.py` riêng. | 15/06/2026 | 15/06/2026 | [Scikit-image Docs](https://scikit-image.org/docs/stable/) |
| 3 | - Cấu hình IAM Role cho SageMaker để đọc được ảnh từ S3 bucket.<br>- Mở SageMaker Studio để thử môi trường. | 16/06/2026 | 16/06/2026 | [SageMaker Execution Roles](https://docs.aws.amazon.com/sagemaker/latest/dg/sagemaker-roles.html) |
| 4 | - Viết script chạy SageMaker Processing Job, chọn máy `ml.m5.xlarge` cho tiết kiệm. | 17/06/2026 | 17/06/2026 | [SageMaker Python SDK](https://sagemaker.readthedocs.io/en/stable/) |
| 5 | - Chạy Job, theo dõi log trên CloudWatch và kiểm tra lại trên S3 xem data đã xử lý và xếp đúng thư mục chưa. | 18/06/2026 | 18/06/2026 | [Amazon CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/) |
| 6 | - Cùng nhóm xem lại AWS Cost Explorer để biết Job hôm qua tốn bao nhiêu.<br>- Phác thảo outline cho Blog 2. | 19/06/2026 | 19/06/2026 | [AWS Billing Console](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/) |

### Thành tựu đạt được
* Bước chuẩn bị dữ liệu giờ chạy hoàn toàn trên Cloud — SageMaker tự lấy, xử lý và lưu lại vào S3 chỉ trong chưa đầy 3 phút.
