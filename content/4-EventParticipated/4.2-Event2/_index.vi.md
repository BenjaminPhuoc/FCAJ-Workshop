---
title: "Event 2"
date: 2026-06-11
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

# BÁO CÁO TỔNG HỢP SỰ KIỆN CLOUD ARCHITECT & TECH TALK (11/06)

## 1. Mô Tả Ngắn Gọn Nội Dung Và Hoạt Động Chính Trong Sự Kiện
Sự kiện gồm hai phần: Chung kết cuộc thi Cloud Architect và chuỗi Tech Talk chuyên sâu từ 3 speaker đại diện cho các công ty công nghệ.

### A. Hoạt động 1: Chung kết Cuộc thi Cloud Architect (Giải Ao làng)
- **Hình thức:** Đấu trắc nghiệm tình huống về kiến trúc đám mây giữa hai đội vào chung kết (nhóm KLK AST và nhóm Ngũ Đại Hiệp).
- **Nội dung xoay quanh:** Các bài toán thực tế trên AWS, bao gồm:
  - Lựa chọn mô hình IaaS (EC2) và quy trình phế hủy thiết bị lưu trữ đúng chuẩn an toàn.
  - Nguyên tắc phân quyền tối thiểu (Least Privilege) khi truy cập S3.
  - Giải pháp cân bằng tải UDP thông lượng cao cho game nhiều người chơi, kết hợp cơ sở dữ liệu key-value (NLB + DynamoDB).
  - Tự động hóa khắc phục lỗi EC2 bằng CloudWatch Logs, Metric Filters & Alarms.
  - Phân phối nội dung bảo mật từ S3 qua CloudFront bằng Origin Access Control (OAC).
  - Thiết kế kết nối hybrid độ trễ thấp, băng thông cao giữa on-prem và nhiều VPC ở các vùng khác nhau (Direct Connect Gateway).
  - Di chuyển database MySQL dung lượng lớn (25TB) từ on-prem lên AWS với downtime tối thiểu (AWS DMS / DataSync / Aurora Replication).
  - Tự động hóa cập nhật AMI/EC2 bằng CloudFormation kết hợp Systems Manager Parameter Store.

### B. Hoạt động 2: Chuỗi chia sẻ chuyên môn từ các Speaker

#### Topic 1: Ứng dụng AI trong Bảo mật Đám mây với AWS Security Agent
*(Speaker: Anh Thịnh - DevOps/DevSecOps Engineer)*
- Chỉ ra những hạn chế của Pentest truyền thống: chi phí cao ($5,000–$20,000/lần), phụ thuộc nhiều vào con người và tốn thời gian.
- Giới thiệu AWS Security Agent, dùng Multi-agent AI / Bedrock để tự động hóa Design Security Review (đánh giá kiến trúc theo chuẩn PCI-DSS, Well-Architected Framework), Code Review (tích hợp CI/CD, rà soát Pull Request trên GitHub/GitLab), và Pentest hệ thống tự động.
- Nêu rõ giới hạn hiện tại: chưa xử lý tự động được các luồng xác thực MFA phức tạp (SSO, OTP qua Email) hay các giao thức đặc thù như mTLS.

#### Topic 2: Quản trị SLA & Hệ thống Monitoring trong Thực tế Doanh nghiệp
*(Speaker: Anh Nam - Infrastructure/Reliability Engineer)*
- Giải thích vì sao SLA quan trọng và trách nhiệm thực sự đằng sau việc giữ cam kết với khách hàng.
- Nhấn mạnh: hạ tầng khỏe không đồng nghĩa với trải nghiệm người dùng tốt, nếu bản thân ứng dụng vẫn lỗi kết nối logic.
- Chu trình quản trị rủi ro: Identify Risk → Monitor Signal → Response (SOP/SNS) → Log & Improve.
- Demo thực tế: dựng Dashboard CloudWatch và cấu hình cảnh báo mất kết nối giữa EC2 (Back-end) và RDS PostgreSQL qua AWS SNS.

#### Topic 3: Lộ trình & Bí quyết Ôn luyện Chứng chỉ AWS Certified Cloud Practitioner (CLF-C02)
*(Speaker: Anh Huy)*
- Tổng quan các cấp độ chứng chỉ AWS (Foundational, Associate, Professional, Specialty).
- Cấu trúc đề thi CLF-C02: 65 câu trắc nghiệm, 120 phút (cộng thêm 30 phút cho thí sinh không dùng tiếng Anh bản ngữ), điểm đạt 700/1000, giá trị 3 năm, lệ phí $100.
- Tỷ trọng 4 miền kiến thức: Cloud Concepts (24%), Security & Compliance (30%), Cloud Technology & Services (34%), Billing & Pricing (12%).
- Mẹo thi: phương pháp loại trừ, mapping từ khóa, luyện tập trên AWS Free Tier, và dùng tính năng đánh dấu câu hỏi (Flag for Review).

## 2. Kết Quả Và Giá Trị Đạt Được

### A. Kiến thức & Bài học chuyên môn
- **Kiến trúc & Hạ tầng Cloud:** Hiểu chắc hơn cách phối hợp các dịch vụ AWS nâng cao (Direct Connect, CloudFront OAC, Auto Scaling, SQS, DMS) cho hạ tầng quy mô lớn, vừa cần tính sẵn sàng cao vừa phải tối ưu chi phí.
- **Tự động hóa Bảo mật (DevSecOps):** Thấy rõ cách Generative AI / Multi-agent đang dần thay đổi việc rà soát lỗ hổng mã nguồn và thiết kế bảo mật ngay từ giai đoạn lên kế hoạch.
- **Tư duy Vận hành Doanh nghiệp (SRE/Reliability):** Nhận ra Monitoring không chỉ là giữ cho các chỉ số "xanh", mà là giữ cho hành trình trải nghiệm của khách hàng không bị gián đoạn và đúng cam kết SLA.

### B. Kỹ năng mới tích lũy
- **Thực hành Cấu hình Giám sát:** Biết tự custom Metric Alarms trên CloudWatch, dựng ma trận cảnh báo qua AWS SNS, và liên kết kiểm tra sức khỏe giữa tầng EC2 và RDS.
- **Kỹ năng Ôn thi Chứng chỉ Quốc tế:** Nắm được cách phân tích từ khóa, phương pháp loại trừ và cách phân bổ thời gian hợp lý cho kỳ thi AWS Practitioner/Associate.

## 3. Tổng Kết Sự Tham Gia Thực Tế & Kinh Nghiệm Tích Lũy
- **Thẩm thấu trải nghiệm thực tế:** Tham dự trực tiếp giúp gắn lý thuyết học được với các sự cố mà doanh nghiệp thực sự gặp phải — như sập kết nối giữa Back-end và Database, script tự động hóa chạy lỗi, hay rủi ro tài chính khi vi phạm SLA.
- **Rèn luyện kỹ năng mềm:** Rèn thêm tư duy phản biện khi phân tích các tình huống kiến trúc trong phần thi, đồng thời học được cách trình bày và xử lý sự cố trực tiếp từ các kỹ sư nhiều kinh nghiệm.
- **Định hướng phát triển bản thân:** Có thêm lộ trình rõ ràng hơn cho việc học Cloud/DevOps, với các mốc chứng chỉ AWS cụ thể để làm dày thêm hồ sơ chuyên môn.

![Event2](/images/4-EventParticipated/event_11-6-26/1.png)
![Event2](/images/4-EventParticipated/event_11-6-26/2.png)
![Event2](/images/4-EventParticipated/event_11-6-26/3.png)
![Event2](/images/4-EventParticipated/event_11-6-26/4.png)
![Event2](/images/4-EventParticipated/event_11-6-26/5.png)
![Event2](/images/4-EventParticipated/event_11-6-26/6.png)
![Event2](/images/4-EventParticipated/event_11-6-26/7.png)
![Event2](/images/4-EventParticipated/event_11-6-26/8.png)
