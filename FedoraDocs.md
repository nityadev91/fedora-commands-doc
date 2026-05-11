# Fedora Linux Common Commands

This document provides a collection of the most common commands for Fedora Linux, organized by category. It includes system administration, package management, Docker, Nginx, and other essential tools.

## System Information

- `uname -a`: Display system information
- `hostname`: Show or set the system's hostname
- `uptime`: Show how long the system has been running
- `whoami`: Display current user
- `id`: Display user and group information
- `date`: Display or set the system date and time
- `cal`: Display a calendar
- `df -h`: Display disk space usage
- `du -h`: Display directory space usage
- `free -h`: Display memory usage
- `top`: Display running processes
- `htop`: Interactive process viewer (install if needed)
- `ps aux`: List all running processes
- `lscpu`: Display CPU information
- `lsblk`: List block devices
- `lspci`: List PCI devices
- `lsusb`: List USB devices

## Package Management (dnf)

- `sudo dnf update`: Update all packages
- `sudo dnf upgrade`: Upgrade all packages
- `sudo dnf install <package>`: Install a package
- `sudo dnf remove <package>`: Remove a package
- `dnf search <term>`: Search for packages
- `dnf info <package>`: Display package information
- `dnf list installed`: List installed packages
- `dnf list available`: List available packages
- `sudo dnf clean all`: Clean package cache
- `sudo dnf autoremove`: Remove unused dependencies
- `sudo dnf groupinstall <group>`: Install a package group
- `sudo dnf groupremove <group>`: Remove a package group
- `dnf history`: View transaction history
- `dnf repoquery <package>`: Query package information

## File and Directory Operations

- `ls -la`: List files with details
- `cd <directory>`: Change directory
- `pwd`: Print working directory
- `mkdir <directory>`: Create directory
- `rmdir <directory>`: Remove empty directory
- `rm -rf <directory>`: Remove directory and contents
- `cp <source> <destination>`: Copy files/directories
- `mv <source> <destination>`: Move/rename files/directories
- `touch <file>`: Create empty file or update timestamp
- `cat <file>`: Display file contents
- `less <file>`: View file with paging
- `head <file>`: Display first lines of file
- `tail <file>`: Display last lines of file
- `tail -f <file>`: Follow file changes
- `grep <pattern> <file>`: Search for pattern in file
- `find <path> -name <pattern>`: Find files by name
- `chmod <permissions> <file>`: Change file permissions
- `chown <user>:<group> <file>`: Change file ownership
- `ln -s <target> <link>`: Create symbolic link
- `tar -czf <archive.tar.gz> <files>`: Create compressed archive
- `tar -xzf <archive.tar.gz>`: Extract compressed archive

## Process Management

- `ps`: Display current processes
- `kill <PID>`: Kill a process by PID
- `killall <process_name>`: Kill processes by name
- `pkill <pattern>`: Kill processes matching pattern
- `bg`: Resume job in background
- `fg`: Bring job to foreground
- `jobs`: List background jobs
- `nice -n <priority> <command>`: Run command with priority
- `renice <priority> <PID>`: Change process priority
- `sudo systemctl start <service>`: Start a service
- `sudo systemctl stop <service>`: Stop a service
- `sudo systemctl restart <service>`: Restart a service
- `systemctl status <service>`: Check service status
- `sudo systemctl enable <service>`: Enable service at boot
- `sudo systemctl disable <service>`: Disable service at boot

## Network Commands

- `ip addr show`: Display IP addresses
- `ip route show`: Display routing table
- `ping <host>`: Test network connectivity
- `traceroute <host>`: Trace network path
- `nslookup <domain>`: DNS lookup
- `dig <domain>`: DNS query
- `netstat -tuln`: Display listening ports
- `ss -tuln`: Display listening sockets
- `curl <url>`: Transfer data from server
- `wget <url>`: Download files
- `scp <source> <destination>`: Secure copy over SSH
- `rsync <source> <destination>`: Sync files/directories
- `ssh <user>@<host>`: Connect via SSH
- `ifconfig`: Display network interfaces (deprecated, use ip)
- `nmcli device status`: NetworkManager device status
- `nmcli connection show`: Show network connections
- `firewall-cmd --list-all`: Display firewall rules

## User Management

- `sudo useradd <username>`: Add a new user
- `sudo userdel <username>`: Delete a user
- `sudo usermod <options> <username>`: Modify user account
- `sudo passwd <username>`: Change user password
- `sudo groupadd <groupname>`: Add a new group
- `sudo groupdel <groupname>`: Delete a group
- `groups <username>`: Show user groups
- `id <username>`: Display user/group IDs
- `su <username>`: Switch user
- `sudo <command>`: Execute command as root
- `sudo visudo`: Edit sudoers file
- `sudo chage <username>`: Change user password expiry

## Docker Commands

- `docker --version`: Check Docker version
- `sudo docker pull <image>`: Pull an image from registry
- `sudo docker images`: List local images
- `sudo docker ps`: List running containers
- `sudo docker ps -a`: List all containers
- `sudo docker run <image>`: Run a container
- `sudo docker run -d <image>`: Run container in background
- `sudo docker run -it <image>`: Run interactive container
- `sudo docker stop <container>`: Stop a container
- `sudo docker start <container>`: Start a stopped container
- `sudo docker restart <container>`: Restart a container
- `sudo docker rm <container>`: Remove a container
- `sudo docker rmi <image>`: Remove an image
- `sudo docker exec -it <container> <command>`: Execute command in container
- `sudo docker logs <container>`: View container logs
- `sudo docker build -t <tag> .`: Build an image from Dockerfile
- `sudo docker-compose up`: Start services with docker-compose
- `sudo docker-compose down`: Stop services with docker-compose
- `sudo docker system prune`: Remove unused data
- `sudo docker volume ls`: List volumes
- `sudo docker network ls`: List networks

## Nginx Commands

- `nginx -v`: Check Nginx version
- `sudo nginx -t`: Test configuration
- `sudo nginx`: Start Nginx
- `sudo nginx -s stop`: Stop Nginx
- `sudo nginx -s reload`: Reload configuration
- `sudo nginx -s restart`: Restart Nginx
- `sudo systemctl start nginx`: Start Nginx service
- `sudo systemctl stop nginx`: Stop Nginx service
- `sudo systemctl restart nginx`: Restart Nginx service
- `sudo systemctl reload nginx`: Reload Nginx configuration
- `systemctl status nginx`: Check Nginx status
- `sudo systemctl enable nginx`: Enable Nginx at boot
- `sudo systemctl disable nginx`: Disable Nginx at boot

## SELinux Commands

- `sestatus`: Display SELinux status
- `sudo setenforce 0`: Set SELinux to permissive mode
- `sudo setenforce 1`: Set SELinux to enforcing mode
- `sudo semanage fcontext -a -t <type> <path>`: Add file context
- `sudo restorecon <path>`: Restore file contexts
- `sudo chcon -t <type> <file>`: Change file context
- `sudo semanage port -a -t <type> -p <protocol> <port>`: Add port context

## Firewall Commands (firewalld)

- `sudo firewall-cmd --state`: Check firewall state
- `sudo firewall-cmd --list-all`: List all firewall rules
- `sudo firewall-cmd --add-service=<service>`: Add service to firewall
- `sudo firewall-cmd --remove-service=<service>`: Remove service from firewall
- `sudo firewall-cmd --add-port=<port>/<protocol>`: Add port to firewall
- `sudo firewall-cmd --remove-port=<port>/<protocol>`: Remove port from firewall
- `sudo firewall-cmd --reload`: Reload firewall rules
- `sudo firewall-cmd --permanent`: Make changes permanent

## Git Commands

- `git init`: Initialize repository
- `git clone <url>`: Clone repository
- `git add <file>`: Add file to staging
- `git add .`: Add all files to staging
- `git commit -m "message"`: Commit changes
- `git status`: Check repository status
- `git log`: View commit history
- `git branch`: List branches
- `git checkout <branch>`: Switch branch
- `git merge <branch>`: Merge branch
- `git pull`: Pull changes from remote
- `git push`: Push changes to remote
- `git remote -v`: List remote repositories

## Text Editors

### Vim
- `vim <file>`: Open file in Vim
- `i`: Enter insert mode
- `Esc`: Exit insert mode
- `:w`: Save file
- `:q`: Quit
- `:wq`: Save and quit
- `:q!`: Quit without saving
- `/<pattern>`: Search forward
- `n`: Next search result

### Nano
- `nano <file>`: Open file in Nano
- `Ctrl+O`: Save file
- `Ctrl+X`: Exit
- `Ctrl+W`: Search
- `Ctrl+K`: Cut line
- `Ctrl+U`: Paste line

## System Monitoring

- `sudo journalctl`: View system logs
- `sudo journalctl -u <service>`: View service logs
- `sudo dmesg`: Display kernel messages
- `sar`: System activity report
- `iostat`: I/O statistics
- `vmstat`: Virtual memory statistics
- `mpstat`: CPU statistics

## Archive and Compression

- `gzip <file>`: Compress file
- `gunzip <file.gz>`: Decompress file
- `bzip2 <file>`: Compress with bzip2
- `bunzip2 <file.bz2>`: Decompress bzip2
- `xz <file>`: Compress with xz
- `unxz <file.xz>`: Decompress xz
- `zip <archive.zip> <files>`: Create zip archive
- `unzip <archive.zip>`: Extract zip archive

## Miscellaneous

- `history`: Display command history
- `alias <name>='<command>'`: Create command alias
- `export <variable>=<value>`: Set environment variable
- `echo $<variable>`: Display environment variable
- `which <command>`: Locate command
- `whereis <command>`: Locate command and documentation
- `man <command>`: Display manual page
- `info <command>`: Display info page
- `sudo shutdown now`: Shutdown system
- `sudo reboot`: Reboot system
- `sudo halt`: Halt system