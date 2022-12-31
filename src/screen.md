## Working with screen

You can use `screen` on the remote server to keep programs running even when 
you're not online.

### Installing screen

If not already there, you can install it to Ubuntu/Debian based system using:

```shell
sudo apt-get install screen
```

### Start a shell in screen

You can start a named screen using the following command:

```shell
screen -S work-thing
```

Names help to organize your screens.

### Detaching from a screen

You can detach from a running screen using keyboard `ctrl-a` and `d`. Every screen
command starts with a `ctrl-a` and is followed by another action key.

### Listing sessions

You can also list your screen sessions:

```shell
$ screen -list
There are screens on:
	10812.pts-1.shell	(04/05/20 19:58:20)	(Detached)
	10800.pts-1.shell	(04/05/20 19:58:18)	(Detached)
2 Sockets in /run/screen/S-bob.
```

### Opening screen session

If there's only one detached session, you can open it using:

```shell
screen -r
```

### Opening previous screen session by id

```shell
screen -r 10812
```

### Opening a previous screen session by name

```shell
screen -r work-thing
```

### Opening an active screen session

Sometimes you may have left the screen session open. You can take over another 
session with the `-d` argument.

```shell
screen -d -r work-thing
```

### Creating new screen windows

You can open multiple screen windows inside a screen session.

To create a new session use the command `ctrl-a` and `c`.

### Moving between screen windows

To move between sessions you can use `ctrl-a` followed by the number between 0 
and 9.

E.g. to move to second screen session, use issue `ctrl-a` followed by `1`. The first sessions is `0`.

### Accidentally opened another screen inside another screen

In case you end up having a screen open inside another screen window, you can 
still issue commands to it using multiple `a` 's. 

E.g. the `ctrl-a`, followed by another `a` and `d` would detach the inner screen.
