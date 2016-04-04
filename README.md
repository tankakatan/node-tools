# node-tools
Node.js server application toolset

## 1. nodeapp

A FreeBSD `rc`-deamon that starts Node server specified with application directory and filename and `node` output location.

The script should be stored at `/usr/local/etc/rc.d`. It uses the standard `/etc/rc.subr` API and `/etc/rc.conf` file that should contain the following parameters:

```bash
# nodeapp server setup
nodeapp_enable="YES"
nodeapp_folder="/path/to/your/application"
nodeapp_script="application-name.js"
nodeapp_output="/path/to/your/log/file.log"
```

The `nodeapp_output` is an optional parameter. If not specified it will be initialized with the default value `/var/log/nodeapp.log`. If any required parameter is missing `nodeapp` will print an error description and fix instructions.
