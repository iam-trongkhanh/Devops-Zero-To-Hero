# Devops-Zero-To-Hero

Linux
- ssh-keygen -t rsa
- /var (lưu các logs của các services)
  sudo du -sh * (xem mức chiếm dụng tài nguyên)

- systemctl status/start/stop <name_service>
- ufw status (check status firewall)
- find /log  -type f/d -name *.log -mtime +7 < -exec ls -ltr {} \; >
- last -F
  last -F | grep "$(date 'date+%b %e')"
