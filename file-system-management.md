# Linux for DevOps Engineers – Part 2: Mastering File System Management

In enterprise DevOps environments, whether you're provisioning cloud VMs or deploying microservices, interacting with the Linux file system is inevitable. This guide is for beginners who want to understand file system commands in Linux with relatable comparisons to Windows OS, and real-world DevOps use cases—especially useful for interviews and hands-on roles.

---

## 1. Navigating the File System

**Purpose:** Move through folders and locate files — similar to using File Explorer in Windows.

### `cd` – Change Directory
```bash
cd /path/to/folder
```
**Windows Equivalent:** `cd` or double-click folder  
**Scenario:** Navigate to `/etc/nginx` to check configuration before restarting the service.

### `pwd` – Print Working Directory
```bash
pwd
```
**Windows Equivalent:** Displays current path in Command Prompt.

### `ls` – List Directory Contents
```bash
ls -l
ls -a
```
**Windows Equivalent:** `dir` or viewing files in File Explorer  
**Scenario:** Confirm that configuration files exist in a folder before applying changes.

---

## 2. Creating, Copying, and Managing Files

**Purpose:** Handle files just like creating, copying, renaming, and deleting in Windows.

### `touch` – Create Empty File
```bash
touch filename.txt
```
**Windows Equivalent:** Right-click → New → Text Document  
**Scenario:** Create placeholder logs or test files in automation.

### `cp` – Copy Files or Directories
```bash
cp file1 file2
cp -r dir1 dir2
```
**Windows Equivalent:** Ctrl+C, Ctrl+V  
**Scenario:** Backup `nginx.conf` before making changes.

### `mv` – Move or Rename
```bash
mv old.txt new.txt
```
**Windows Equivalent:** Rename or drag to another folder

### `rm` – Delete Files or Directories
```bash
rm file
rm -r folder/
```
**Windows Equivalent:** Delete or Shift+Del  
**Scenario:** Remove logs from `/var/log` to reclaim disk space.

### `mkdir` – Make Directory
```bash
mkdir myfolder
```

### `rmdir` – Remove Empty Directory
```bash
rmdir myfolder
```

---

## 3. Viewing File Content

**Purpose:** Read contents of config/log files without opening a GUI.

### `cat`, `less`, `more`
```bash
cat file.txt
less file.txt
```
**Scenario:** Browse large logs without opening a full editor.

### `head`, `tail`
```bash
head -n 10 logfile
tail -f logfile
```
**Scenario:** Monitor logs in real time after deploying a service.

---

## 4. File Permissions & Ownership

**Purpose:** Secure files and control who can read/write/execute them.

### `chmod` – Change File Permissions
```bash
chmod 755 script.sh
```

#### Permission Bits
- `r = 4` (read)
- `w = 2` (write)
- `x = 1` (execute)

**Example:**
- `chmod 644 file` → Owner: read/write, Others: read only  
- `chmod +x script.sh` → Make script executable

**Windows Equivalent:** File Properties → Security

**Scenario:** Set deploy scripts to be executable only by Jenkins or the owner.

### `chown` – Change File Ownership
```bash
chown user:group file
```
**Scenario:** You uploaded files as root but need them owned by `nginx`.

### `ln -s` – Create Symbolic Links
```bash
ln -s /path/original /path/shortcut
```
**Windows Equivalent:** Shortcut files

---

## 5. Disk Space & Usage

**Purpose:** Monitor and troubleshoot space-related issues.

### `df -h` – View Free Disk Space
**Scenario:** Check if `/var` is full before deploying or upgrading.

### `du -sh` – Check Folder Size
```bash
du -sh /var/log
```
**Scenario:** Identify disk-hogging folders to clean up.

---

## 6. Searching & Filtering

**Purpose:** Locate files or specific log entries.

### `find` – Search for Files
find / -name "nginx.conf"
```

### `grep` – Search Inside Files
```bash
grep "ERROR" /var/log/syslog
```
**Scenario:** Search error patterns across logs after a failed deploy.

---

## Final Thoughts

Mastering these file system commands gives you the power to navigate, organize, and secure Linux environments confidently—especially important in enterprise DevOps roles.
If you're preparing for interviews, be ready to explain:

- How you’d investigate a full disk on a Linux VM
- How to ensure only Jenkins can run a deployment script
- What commands you’d use to troubleshoot logs after a failed deployment

---

**Missed Part 1?**  
➡️ [Linux User & Group Management](./user-group-admin.md)


