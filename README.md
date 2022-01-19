# Configuration for multiple SSH keys

## Create different public keys

You probably wanto to generate two or more of them, each through this command:

```
 $ ssh-keygen -t rsa -C "Your comment"
```
> Generate a key of type RSA and add a comment of your choice to ease key identification.

you can check your keys in the following directory:

```
 $ ~/.ssh/ 
```

You can see active keys through:
```
 $ ssh-add -l
```

if you can't find yours, you may add them:
```
 $ ssh-add ~/.ssh/key_name 
```
> Key will be named after your comment by default.

```
 $ git config user.name "yourname"
 $ git config user.email "respectivemail@mail.com" 
```

You can also have global credentials configured (those will be used if you don't set them inside a git folder as the previous step shows): 

```
 $ git config --global user.name "yourname" 
 $ git config --global user.email "respectivemail@mail.com"
```

## Finally

```
$ git add .
$ git commit -m "your commit message"
$ git push
```

### <a id="first-commit">First commit</a>

If this is your first commit after a ```$ git init```, make sure you already have the repo on your account, credentials set, and go for:


```
$ git remote add origin git@github.com:zerkeizi/yourrepo.git
$ git push --set-upstream origin master
```