# Screen Commands

### Install

#### Ubuntu and Debian OS
```
sudo apt install screen
```

#### CentOS and Fedora
```
sudo apt install screen
```

### Version
```console
bash-3.2:~$ screen -version
Screen version 4.00.03 (FAU) 23-Oct-06
```

### Starting linux screen
```console
bash-3.2:~$ screen
```

### Starting named session
```console
bash-3.2:~$ screen -S session_name
```

### Detach from screen session
Detach from the screen session at any time by typing
`Ctrl+a` `d`

### List the running screen session
```console
bash-3.2:~$ screen -ls
There are screens on:
	827.ui	(Detached)
	1069.api	(Detached)
2 Sockets in /var/folders/y9/03x2wp3931s5mfwlhth7k0xm0000gq/T/.screen.
```

### Reattach to screen session
```console
bash-3.2:~$ screen -r 827
```

### Quit screen session
```console
bash-3.2:~$ screen -XS 827 quit
```

### Screen window shortcuts

+ `Ctrl+a` `c` Create a new window (with shell)
+ `Ctrl+a` `"` List all window
+ `Ctrl+a` `0` Switch to window 0 (by number )
+ `Ctrl+a` `A` Rename the current window
+ `Ctrl+a` `S` Split current region horizontally into two regions
+ `Ctrl+a` `|` Split current region vertically into two regions
+ `Ctrl+a` `tab` Switch the input focus to the next region
+ `Ctrl+a` `Ctrl+a` Toggle between the current and previous region
+ `Ctrl+a` `Q` Close all regions but the current one
+ `Ctrl+a` `X` Close the current region
+ `Ctrl+a` `k` Quit current screen window