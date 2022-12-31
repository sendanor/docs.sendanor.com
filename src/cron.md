# Cron 

Cron is a daemon that runs scheduled tasks on a Linux system. These tasks are 
called "cron jobs" and are defined in a configuration file called a crontab. 
Cron is often used to schedule tasks to run automatically at a specific time or 
at a specified interval.

Cron jobs are typically used for tasks that need to be run on a regular basis, 
such as system maintenance tasks, backups, and other automated processes. For 
example, you could use crontab to schedule a script to run every day at midnight 
to update a database, or to run a backup script every week.

Crontab is a powerful tool that allows you to automate a wide variety of tasks 
on your Linux system. It is commonly used in conjunction with shell scripts, but 
can be used to run any command or script that is executable on the system.

### How to use crontab on a Linux system

1. Open a terminal and enter the command `crontab -e`. This will open the 
   crontab configuration file in a text editor. If this is the first time you 
   are using crontab, you will be asked to choose a text editor.

2. To create a new cron job, add a new line to the crontab configuration file in
   the following format:
   ```
   * * * * * command_to_execute
   ```
   
   The asterisks represent the following:
   - The first asterisk represents the minute (0-59)
   - The second asterisk represents the hour (0-23)
   - The third asterisk represents the day of the month (1-31)
   - The fourth asterisk represents the month (1-12)
   - The fifth asterisk represents the day of the week (0-6, where 0 
     represents Sunday)
   
   For example, to run a command at 10:15 every day, you would enter the 
   following line in the crontab configuration file:
   ```
   15 10 * * * command_to_execute
   ```
   
   You can also use special characters to specify more complex scheduling 
   patterns. 
   
   For example, to run a command every hour at 15 minutes, you can use the 
   `15` in the minute field and character `*` in the hour field:
   ```
   15 * * * * command_to_execute
   ```

   Or, to run a command every 5 minutes, you can use the character `*/5` in 
   the minute field:

   ```
   */5 * * * * command_to_execute
   ```

3. Save and close the crontab configuration file. The cron daemon will 
   automatically pick up the changes and start running the new cron job.

4. To view your current cron jobs, enter the command `crontab -l`.

5. To remove a cron job, edit the crontab configuration file and delete the line 
   that corresponds to the cron job you want to remove. Save and close the 
   file, and the cron daemon will automatically pick up the changes.

### Running cron task when the server starts

The `@reboot` rule is a special keyword that can be used in place of the timing 
fields (minute, hour, day of month, month, and day of week) to specify that a
cron job should be run when the system reboots. This can be useful for tasks 
that need to be run every time the system starts up, such as starting a service
or running a script.

To use the `@reboot` rule, simply add it as the first field in the crontab 
configuration file, followed by the command to be executed:
```
@reboot command_to_execute
```

For example, to run a script every time the system reboots, you could add the
following line to the crontab configuration file:
```
@reboot /path/to/script.sh
```

Note that the `@reboot` rule is only processed when the cron daemon is started,
which typically happens when the system boots. If the cron daemon is already 
running when you add a new `@reboot` rule, it will not be executed until the
next time the system reboots.

### Cron service environment

Cron jobs are typically run in a limited environment, which means that certain 
environmental variables and paths may not be set up as they are in a normal 
interactive shell session. This can cause problems when running scripts or 
commands that rely on these variables or paths being set correctly.

One common issue that can arise is that the `PATH` variable may not be set to 
include all the directories that you need to access. The `PATH` variable is 
a list of directories that the shell searches for executables when you run a
command. If a command is not found in the directories listed in `PATH`, the 
shell will not be able to find and execute it.

To configure the `PATH` variable correctly for your cron jobs, you can add the 
following line to the top of your crontab configuration file:
```
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
```

This sets the `PATH` variable to a default value that includes common 
directories where executables are typically stored. You can also add additional 
directories to the `PATH` variable as needed, separated by colons.

For example, if you want to include the `/usr/local/bin` directory in the `PATH` 
variable, you can add it as follows:
```
PATH=/usr/local/bin:/usr/local/sbin:/usr/sbin:/usr/bin:/sbin:/bin
```
