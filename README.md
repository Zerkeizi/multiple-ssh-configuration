# Configuration for multiple SSH keys
> This trick can be used to ease the process when using SSH for authentication. It can either be used to access a webserver or manage a git repository by terminal.

<br>

## 2. Create different public keys

Generally, SSH keys are kept in this folder, you can check your current ones:
```
 $ ls ~/.ssh/ 
```


Since I'll be creating multiple keys, I am organizing them in separated folders
```
 $ cd ~/.ssh/ 
 $ mkdir work
 $ mkdir personal
```

For each of them I'll be running:
```
 $ ssh-keygen -t rsa -C "Your comment"
```
> Before heading to the next steps, make sure you have a pair of keys inside each folder

<br/>

## 2. The <b>config</b> file:

Create a config file inside `/.ssh/` folder
```
$ touch config
```

Set it as so:
```
Host mine
   HostName github.com
   User git
   IdentityFile ~/.ssh/personal/id_rsa

Host theirs
    HostName github.com
    User git
    IdentityFile ~/.ssh/work/id_rsa
```

Now, <b>mine</b> is an alias for my first settings. I could set other things beyond HostName, User and IdentityFile. Like port. <br/>We use the alias as a reference:
```
git clone mine:zerkeizi/multiple-ssh-configuration.git
```

Thats it. 

<br/>