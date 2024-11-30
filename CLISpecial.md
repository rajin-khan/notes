# ~ 💻 Useful CLI Commands ~

## Directory & File Management:
- **Create multiple folders**:  
  ```bash
  mkdir -p {dev,test,prod}/{backend,frontend}
  ```

- **Create multiple files**:  
  ```bash
  touch test{1..100}.txt
  ```

## Navigation:
- **Return to previous directory**:  
  ```bash
  cd -
  ```

## Real-time file monitoring:
- **Follow file updates**:  
  ```bash
  tail -f error_file.log
  ```

## Command History:
- **View last 5 commands**:  
  ```bash
  history 5
  ```

- **Re-execute a command**:  
  ```bash
  !<command number>
  ```

# Additional Useful Linux & Mac Commands

## Network & System Monitoring:
- **Check weather**:  
  ```bash
  curl http://wttr.in/
  ```

- **Speed test**:  
  ```bash
  networkquality -v
  ```

- **Battery health**:  
  ```bash
  system_profiler SPPowerDataType | grep -A3 -B7 "Condition"
  ```

## Network & IP:
- **Get public IP address**:  
  ```bash
  ipconfig getifaddr en0
  ```

- **Traceroute to website**:  
  ```bash
  traceroute <website.com>
  ```

## Disk & File Management:
- **Check storage usage**:  
  ```bash
  ncdu
  ```

- **Erase a disk**:  
  ```bash
  diskutil list
  diskutil eraseDisk FAT32 UNTITLED MBRFormat /dev/diskN
  ```

## System Stats:
- **View running processes**:  
  ```bash
  top
  ```

- **M1 specific tools**:  
  ```bash
  asitop
  btop
  ```
