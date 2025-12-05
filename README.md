# Devops-Zero-To-Hero

Linux

- ssh-keygen -t rsa
- /var (lưu các logs của các services)
  sudo du -sh \* (xem mức chiếm dụng tài nguyên)

- systemctl status/start/stop <name_service>
- ufw status (check status firewall)
- find /log -type f/d -name \*.log -mtime +7 < -exec ls -ltr {} \; >
- last -F
  last -F | grep "$(date 'date+%b %e')" | aws '{print $1}' | sort | uniq

Networking

- OSI model

  - Giống 1 bản thiết kế chi tiết giúp hiểu và xây dựng mạng
  - 1 mô hình chung giúp các thiết bị giao tiếp với nhau
  - Layer 7: Application: trình duyệt web dùng http, email dùng smtp tương tác trực tiêp với mạng
  - Layer 6: Presentation Đảm bảo dữ liệu định dạng đúng, mã hoá data
  - Layer 5: Session Giữ kết nối ổn định
  - Layer 4: Transport: Đảm bảo dữ liệu được gửi đi, chia nhỏ dữ liệu thành các segments, TCP thì tin cậy, UDP thì nhanh
  - Layer 3: Network: tìm đường đi tốt nhất cho các packets dựa trên IP ( Router hoạt động ở đây)
  - Layer 2: DataLink: Đảm bảo truyền giữ liệu 1 cách tin cậy giữa 2 thiết bị 1 cách trực tiếp trong cùng 1 mạng LAN(MAC) switch làm việc ở đây
  - Layer 1: Physical: Liên quan dây cap mạng, sóng wifi, việc truyền tín hiệu điện, tín hiệu quang bằng bit 0, 1

  - Load Blancer: Tập trung vào health check, loại bỏ các máy chủ gặp sự cố, phân phối cập 1 cách hiệu quả dựa trên IP, port kết hợp với health check, hoạt động layer 4, 7. Phân tích nội dung gói tin tại layer 7
  - Reverse Proxy: Như 1 lớp áo chắn cho backend phía sau, cách request không hợp lệ, hay độc hại sẽ bị chặn lại, ví dụ như authentication,SSL termination, WAF, có cách tính năng giúp backend phía sau như catching, load balancing, hoạt động lại layer 7
  -
  - API Gateway: là 1 loại reverse proxy đời mới, được cấu hình thông qua api, giao diện thay vì cấu hình qua file như reverse proxy thông thường, cung cấp cách thức cấu hình, theo dõi quan sát. Hoạt động ở layer 4, 7
