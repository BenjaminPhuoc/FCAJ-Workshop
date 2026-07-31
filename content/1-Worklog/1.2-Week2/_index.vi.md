---
title: "Tuần 2"
date: 2026-06-08
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2
* Dựng một bộ Toy Dataset nhỏ gọn để chạy thử training, tránh tốn tiền AWS.
* Viết và nộp xong bài Blog công nghệ đầu tiên.

### Tiến độ công việc
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Chốt kiến trúc cùng nhóm: chuyển hẳn sang Serverless (API Gateway + Lambda + SageMaker) để tối ưu chi phí vận hành. | 08/06/2026 | 08/06/2026 | [AWS Serverless Architecture](https://aws.amazon.com/serverless/) |
| 3 | - Nhận phần viết script `create_toy_dataset.py`, random lấy 120 ảnh X-Quang phổi, cân bằng đều giữa các class. | 09/06/2026 | 09/06/2026 | [Python Pandas Docs](https://pandas.pydata.org/docs/) |
| 4 | - Chạy script chia data, kiểm tra lại cấu trúc folder Train/Val.<br>- Song song đó, bạn cùng nhóm dựng S3 bucket. | 10/06/2026 | 10/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/) |
| 5 | - Dùng AWS CLI sync toàn bộ Toy Dataset lên S3 bucket của dự án. | 11/06/2026 | 11/06/2026 | [AWS CLI S3 Commands](https://docs.aws.amazon.com/cli/latest/reference/s3/) |
| 6 | - Cùng nhóm hoàn thiện và format bài Blog số 1 "Kiến trúc Serverless MLOps" trước khi nộp. | 12/06/2026 | 12/06/2026 | [Quy định FCAJ Blog](https://cloudjourney.awsstudygroup.com/) |

### Thành tựu đạt được
* Đưa được bộ data thu gọn lên S3 — từ giờ test code chỉ mất 1-2 phút, đúng chuẩn FinOps.
* Nộp bài Blog 1 đúng hạn.
