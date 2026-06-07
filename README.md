1. The Foundation (System & Security)
Before you can manage servers, you need to navigate them comfortably and understand who owns what.

Key Concepts to Master:
Files & Directories: Master the Filesystem Hierarchy Standard (FHS). Know the difference between /etc (configurations), /var (log files), and /home (user data). Learn navigation shortcuts like cd ~, cd -, and ls -la.

Permissions: Understand the rwx (Read, Write, Execute) triplets for User, Group, and Others.

Practice both absolute (numeric) and symbolic modes: chmod 755 script.sh vs. chmod +x script.sh.

Learn chown to change file ownership.

Users & Groups: Learn how to create users (useradd), manage passwords (passwd), and grant administrative privileges via the /etc/sudoers file or by adding users to the sudo group.

💡 Pro-Tip: Never log in directly as root for daily tasks. Always use a standard user with sudo privileges. It's the first rule of Linux security.

2: Connectivity & Observability

This week is all about making your server talk to the world securely and figuring out what’s happening under the hood.

Key Concepts to Master:
Networking: Learn basic diagnostic tools: ip a (interfaces), ping (connectivity), ss -tulpn (checking active ports), and curl (testing web responses).

SSH (Secure Shell): This is your lifeline. Move away from password logins immediately. Master Key-Based Authentication (ssh-keygen and ssh-copy-id). Learn how to harden SSH by editing /etc/ssh/sshd_config (e.g., changing the default port 22 or disabling root login).

Services: Understand systemd. You should be able to start, stop, enable (start at boot), and check the status of any service using systemctl.

Logs: Your primary troubleshooting tool. Learn how to navigate /var/log/syslog or /var/log/auth.log. Master journalctl to view systemd logs in real-time (journalctl -f -u nginx).

3: Automation & Data Manipulation

Time to make Linux do the heavy lifting for you.

Key Concepts to Master:
Bash Scripting: Start with variables, conditional statements (if/else), and loops (for/while). Always start your scripts with the proper shebang: #!/bin/bash.

Text Processing: The "Big Three" of Linux text manipulation:

grep: Finding patterns in files (e.g., grep "Error" /var/log/nginx/error.log).

awk: Great for extracting specific columns of data (e.g., printing just the IP addresses from a log).

sed: Perfect for find-and-replace tasks directly inside text files.

Cron Jobs: Understand the 5-star cron syntax (* * * * * -> Minute, Hour, Day of Month, Month, Day of Week). Use crontab -e to schedule your automation scripts.

4: Modern Infrastructure & Troubleshooting

Tying it all together with modern deployment methods and learning how to fix things when they break.

Key Concepts to Master:
Docker on Linux: Understand the architecture (Engine vs. Client). Learn how to pull images, run containers (docker run -d -p 80:80 nginx), manage volumes for persistent data, and view container logs.

System Troubleshooting: Learn how to diagnose a sluggish server:

CPU/Memory: top, htop, or free -m.

Disk Space: df -h (disk usage) and du -sh * (finding large directories).

App Deployment: Combine your networking and service knowledge to host a simple web page or app, ensuring firewalls (like ufw) allow the necessary traffic.
