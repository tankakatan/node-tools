# node-tools
Node.js server application toolset

## 1. nodeapp

A FreeBSD `rc.d` script that starts arbitrary Node.js application and writes it's log into a file.

### 1.1. Installation

```bash
git clone https://github.com/tankakatan/node-tools.git
cp node-tools/nodeapp /usr/local/etc/rc.d/
```

### 1.2. Initial setup

Before running the script you need to enable it in `/etc/rc.conf` file. Also `nodeapp` requires the application name and directory path. Optioanally you can specify `node` log file location.

```bash
# Complete nodeapp config for /etc/rc.conf
nodeapp_enable="YES"
nodeapp_folder="/path/to/your/application"
nodeapp_script="application-name.js"
nodeapp_output="/path/to/your/log/file.log"
```

If `nodeapp_output` parameter is not specified application will write it's log into default `/var/log/nodeapp.log` file.

### 1.3. Usage

`nodeapp` conforms to the standard `/etc/rc.subr` API and accepts common `rc` commands.

```bash
/usr/local/etc/rc.d/nodeapp start
/usr/local/etc/rc.d/nodeapp status
/usr/local/etc/rc.d/nodeapp restart
/usr/local/etc/rc.d/nodeapp stop
...
```

If any required parameters are missing from config, the script will report an error and provide you with fix instructions.
