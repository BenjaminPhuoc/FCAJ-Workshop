---
title: "Event 1"
date: 2026-06-06
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# BÀI THU HOẠCH "MULTIPLAYER GAME NETWORKING WORKSHOP"

## Mục Đích Của Sự Kiện
* **Chia sẻ về các giao thức mạng** dùng trong phát triển game nhiều người chơi (Multiplayer Game).
* **Hướng dẫn quy trình** xây dựng hệ thống WebSocket Serverless trên nền tảng AWS.
* **Demo lập trình mạng** phía Client bằng Game Engine Godot.
* **Giới thiệu cách đóng gói** ứng dụng bằng công nghệ Containerization (Docker).

---

## Nội Dung Nổi Bật

### 1. So sánh các giao thức mạng trong game Multiplayer
* **HTTP Polling:** 
  * Cơ chế: Client liên tục gửi request để kiểm tra update từ Server.
  * Nhược điểm: Độ trễ phản hồi cao (High Latency), gây thêm tải cho hệ thống.
  * Ứng dụng: Chỉ phù hợp cho các tính năng đơn giản như Login hay Leaderboard, không hơn.
* **UDP (User Datagram Protocol):**
  * Cơ chế: Truyền gói tin nhanh, chấp nhận mất gói (Packet loss) để đổi lấy độ trễ cực thấp.
  * Ứng dụng: Lựa chọn tối ưu cho các game tốc độ cao (FPS, MOBA, Đua xe).
  * Trong Godot: Được đóng gói thành thư viện ENet.
* **WebSocket:**
  * Cơ chế: Kết nối hai chiều liên tục, vượt trội hơn HTTP Polling về tính Real-time và kiểm soát dữ liệu ổn định hơn.
  * Ứng dụng: Được chọn làm giải pháp Demo cho game Kéo-Búa-Bao.

### 2. Dựng hệ thống WebSocket Serverless trên AWS
Logic xử lý mạng chạy trên 4 dịch vụ cốt lõi:
* **API Gateway:** Điều hướng kết nối qua các route `$connect`, `$disconnect` và `$default` (định dạng JSON, dựa trên `request.body.action`).
* **Lambda Function:** Xử lý logic nghiệp vụ cho sự kiện kết nối/ngắt kết nối và truyền nhận message.
* **DynamoDB Table:** Lưu dữ liệu trận đấu và trạng thái người chơi qua 5 cột chính: `Connection ID`, `Status` (waiting/playing), `Opponent ID`, `Choice` (kéo/búa/bao) và `Create At` (timestamp).
* **CloudWatch:** Tự động ghi log hệ thống, hỗ trợ theo dõi luồng dữ liệu và debug.

### 3. Lập trình phía Client trên Godot Engine
4 nhiệm vụ chính để giữ kết nối game ổn định:
* **Khởi tạo:** Mở kết nối đến URL của API Gateway qua đối tượng `WebSocketPeer`.
* **Kiểm tra tin nhắn (Message Polling):** Liên tục kiểm tra dữ liệu từ server (kiểu như check hộp thư) mà không làm quá tải hệ thống.
* **Quản lý kết nối (State Management):** Theo dõi 4 trạng thái của WebSocket — `Connecting`, `Open`, `Closing`, `Closed` — để đưa ra yêu cầu tìm trận (Matchmaking) phù hợp.
* **Xử lý dữ liệu:** Giải mã gói tin JSON từ Server để xử lý kết quả trận đấu.

### 4. Ứng dụng công nghệ Containerization (Docker)
* **Giải quyết xung đột môi trường:** Xóa sổ triệt để tình trạng "code chạy được trên máy tôi nhưng lỗi trên máy bạn".
* **So sánh Virtual Machine vs Container:** VM chạy nặng vì phải boot riêng một hệ điều hành; Container nhẹ hơn nhiều nhờ dùng chung OS thông qua Container Engine.
* **Cơ chế Docker Cache/Layer:** Build ảnh theo từng layer, lưu lại lịch sử các bước trước, chỉ build lại layer có thay đổi — giúp rút ngắn đáng kể thời gian đóng gói.

---

## Những Gì Học Được

### Tư Duy Thiết Kế
* **Kịch bản lỗi thực tế:** Học được cách xử lý tình huống ngắt kết nối đột ngột (điều khó tránh khỏi trên mạng) để không tạo ra "Ghost Connection" trong DynamoDB làm lỗi ghép cặp cho người chơi mới.
* **Tối ưu hóa hiệu năng:** Nhận ra rằng dùng `Scan Table` trên DynamoDB để tìm trận sẽ thành nút thắt cổ chai khi lượng user tăng, nên cần một giải pháp quản lý tập trung chuyên biệt hơn.
* **Quản lý tài nguyên hệ thống:** Hiểu rõ tính Stateless của Lambda để từ đó thiết kế cấu trúc lưu trữ hợp lý khi làm tính năng Reconnect.

### Kiến Trúc Kỹ Thuật
* **Lập trình mạng chuyên sâu:** Nắm được cấu trúc gói tin JSON và cách viết logic đồng bộ dữ liệu giữa Game Client và Cloud Server.
* **Ứng dụng thực tế của Docker:** Biết viết một `Dockerfile` hoàn chỉnh (`FROM`, `RUN`, `COPY`, `EXPOSE`...) và hiểu bản chất của `docker run -it` — đủ để dựng môi trường sandbox cô lập hoàn toàn phục vụ test bảo mật và cách ly mã độc.

### Định Hướng Tương Lai
* **AWS GameLift:** Có thêm hướng tư duy về việc host server game trên các cụm EC2 chuyên dụng và tích hợp thuật toán ghép trận tự động nâng cao cho các dự án lớn hơn.

---

## Ứng Dụng Vào Công Việc

1. **Áp dụng cơ chế WebSocket:** Thay thế HTTP truyền thống bằng giao tiếp real-time qua WebSocket trong các dự án cá nhân hoặc đồ án môn học.
2. **Xây dựng cụm Serverless trên AWS:** Thử kết hợp API Gateway và Lambda cho các ứng dụng cần luồng dữ liệu bất đồng bộ.
3. **Chuẩn hóa quy trình đóng gói ứng dụng:** Dùng Docker để đóng gói sản phẩm, giúp cả nhóm chạy chung một môi trường, tối ưu workflow phát triển.
4. **Ứng dụng Sandbox Container:** Tận dụng cơ chế cô lập của Docker để việc test phần mềm và kiểm tra bảo mật an toàn hơn.

---

## Bài Học Rút Ra & Cảm Nhận

Buổi workshop này thực sự đáng giá — vừa có chiều sâu kỹ thuật về mạng ứng dụng trong game, vừa mang lại tư duy DevOps hiện đại.

### 1. Học hỏi từ những nội dung chia sẻ thực tế
* Diễn giả chia sẻ những bài học xương máu về lỗi hệ thống, cách thiết kế và vận hành hạ tầng mạng sao cho cân bằng giữa hiệu năng và chi phí trong thực tế.
* Qua phần phân tích sâu về UDP, WebSocket và cơ chế lưu trữ của DynamoDB, em hiểu rõ hơn cách dữ liệu được xử lý bất đồng bộ trong một hệ thống phân tán.

### 2. Trải nghiệm kỹ thuật thực tế
* Theo dõi demo kết nối trực tiếp giữa Game Client (Godot) và Server (AWS), quan sát luồng dữ liệu từ lúc Client gửi request cho đến khi DynamoDB cập nhật trạng thái.
* Học được cách debug, theo dõi hệ thống qua CloudWatch, cùng vài thao tác tương tác sâu hơn với Docker container qua terminal.

### 3. Ứng dụng tư duy công nghệ hiện đại
* Hiểu rõ hơn tầm quan trọng của ảo hóa và đóng gói ứng dụng bằng Docker trong việc giải phóng lập trình viên khỏi các vấn đề cấu hình môi trường.
* Biết cách dùng Docker Container như một môi trường "Sandbox" an toàn, linh hoạt cho việc test và kiểm tra bảo mật.

### 4. Kết luận & Bài học cốt lõi
* **Thiết kế hệ thống nào cũng phải đánh đổi (Trade-offs)** giữa hiệu năng, độ tin cậy và chi phí — không có công nghệ nào hoàn hảo tuyệt đối, chỉ có công nghệ phù hợp nhất với bài toán cụ thể.
* **Ý thức tối ưu chi phí Cloud:** Luôn phải kiểm tra và tắt các máy chủ/dịch vụ không dùng đến (cụm EC2, Database...) để tránh phát sinh chi phí ngoài dự tính trong quá trình phát triển (một bài học rút ra từ chính hóa đơn Cloud).

> **Tổng kết:** Không chỉ mang lại kiến thức kỹ thuật mạng chuyên sâu, sự kiện này còn thay đổi cách em nhìn nhận về thiết kế kiến trúc hệ thống, tối ưu hạ tầng Cloud và chuẩn hóa quy trình đóng gói phần mềm trong các dự án công nghệ thực tế.

![Event1](/images/4-EventParticipated/event_6-6-26/1.png)
![Event1](/images/4-EventParticipated/event_6-6-26/2.png)
![Event1](/images/4-EventParticipated/event_6-6-26/3.png)
![Event1](/images/4-EventParticipated/event_6-6-26/4.png)
