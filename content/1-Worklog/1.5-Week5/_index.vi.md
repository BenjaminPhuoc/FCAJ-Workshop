---
title: "Tuần 5"
date: 2026-06-29
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5
* Chạy HPO để máy tự tìm bộ tham số tốt nhất cho model, khỏi phải dò tay.
* Viết và nộp xong bài Blog số 2.

### Tiến độ công việc
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Khai báo Search Space cho HPO: learning rate từ `1e-5` đến `1e-2`, batch size 16 hoặc 32. | 29/06/2026 | 29/06/2026 | [SageMaker HPO Guide](https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning.html) |
| 3 | - Cấu hình `HyperparameterTuner`, chọn Recall làm Objective Metric cần tối đa hóa. | 30/06/2026 | 30/06/2026 | [Boto3 HyperparameterTuner API](https://sagemaker.readthedocs.io/en/stable/api/training/tuner.html) |
| 4 | - Chạy HPO Job, cho chạy tối đa 3 job song song để đỡ mất thời gian chờ. | 01/07/2026 | 01/07/2026 | [AWS Tuning Best Practices](https://docs.aws.amazon.com/sagemaker/latest/dg/automatic-model-tuning-considerations.html) |
| 5 | - Job chạy xong, cùng nhóm xem biểu đồ so sánh trên SageMaker Studio và chọn ra model có Recall cao nhất. | 02/07/2026 | 02/07/2026 | [SageMaker Studio Analytics](https://docs.aws.amazon.com/sagemaker/latest/dg/studio-analyze.html) |
| 6 | - Viết xong bài Blog 2 và nộp lên hệ thống. | 03/07/2026 | 03/07/2026 | [Quy định FCAJ Blog](https://cloudjourney.awsstudygroup.com/) |

### Thành tựu đạt được
* Tìm ra được bộ tham số tốt nhất một cách có hệ thống, không cần sửa code chạy tay nhiều lần.
* Đăng bài Blog công nghệ số 2 thành công.
