# PM2 - Process Manager for node.js

## Installation
```bash
$ npm install pm2@latest -g
# or
$ yarn global add pm2
```

## Start an app
The simplest way to start, daemonize and monitor your application is by using this command line:

```bash
$ pm2 start app.js
```
Or start any other application easily:
```bash
$ pm2 start bashscript.sh
$ pm2 start python-app.py --watch
$ pm2 start binary-file -- --port 1520
```
Some options you can pass to the CLI:
```bash
# Specify an app name
--name <app_name>

# Watch and Restart app when files change
--watch

# Set memory threshold for app reload
--max-memory-restart <200MB>

# Specify log file
--log <log_path>

# Pass extra arguments to the script
-- arg1 arg2 arg3

# Delay between automatic restarts
--restart-delay <delay in ms>

# Prefix logs with time
--time

# Do not auto restart app
--no-autorestart

# Specify cron for forced restart
--cron <cron_pattern>

# Attach to application log
--no-daemon
```

## Managing processes
Managing application state is simple here are the commands:
```bash
$ pm2 restart app_name
$ pm2 reload app_name
$ pm2 stop app_name
$ pm2 delete app_name
```
Instead of `app_name` you can pass:
+ all to act on all processes
+ id to act on a specific process id

## List managed applications
List the status of all application managed by PM2:
```bash
$ pm2 list
```

## Display logs
To display logs in realtime:
```bash
$ pm2 logs
```
To dig in older logs:
```bash
$ pm2 logs --lines 200
```

## Terminal Based Dashboard
```bash
pm2 monit
```

## Setup startup script
Restarting PM2 with the processes you manage on server boot/reboot is critical. To solve this, just run this command to generate an active startup script:
```bash
$ pm2 startup
```
And to freeze a process list for automatic respawn:
```bash
$ pm2 save
```

## CheatSheet
Here are some commands that are worth knowing. Just try them with a sample application or with your current web application on your development machine:
```bash
# Fork mode
pm2 start app.js --name my-api # Name process

# Cluster mode
pm2 start app.js -i 0        # Will start maximum processes with LB depending on available CPUs
pm2 start app.js -i max      # Same as above, but deprecated.
pm2 scale app +3             # Scales `app` up by 3 workers
pm2 scale app 2              # Scales `app` up or down to 2 workers total

# Listing

pm2 list               # Display all processes status
pm2 jlist              # Print process list in raw JSON
pm2 prettylist         # Print process list in beautified JSON

pm2 describe 0         # Display all informations about a specific process

pm2 monit              # Monitor all processes

# Logs

pm2 logs [--raw]       # Display all processes logs in streaming
pm2 flush              # Empty all log files
pm2 reloadLogs         # Reload all logs

# Actions

pm2 stop all           # Stop all processes
pm2 restart all        # Restart all processes

pm2 reload all         # Will 0s downtime reload (for NETWORKED apps)

pm2 stop 0             # Stop specific process id
pm2 restart 0          # Restart specific process id

pm2 delete 0           # Will remove process from pm2 list
pm2 delete all         # Will remove all processes from pm2 list

# Misc

pm2 reset <process>    # Reset meta data (restarted time...)
pm2 updatePM2          # Update in memory pm2
pm2 ping               # Ensure pm2 daemon has been launched
pm2 sendSignal SIGUSR2 my-app # Send system signal to script
pm2 start app.js --no-daemon
pm2 start app.js --no-vizion
pm2 start app.js --no-autorestart
```