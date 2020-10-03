# Multiple SSH Keys settings for different github account

## Create different public key

You are going to make two or more of them, each through this command:
```
 $ ssh-keygen -t rsa -C "respectivemail@mail.com"
```
you can check your keys at:
```
 $ ~/.ssh/ 
```

you can see added keys through:
 $ ssh-add -l

if you can't find yours, you may use:
```
 $ ssh-add ~/.ssh/key_name 
```

## Create an SSH config

```
 $ cd ~/.ssh/
 $ touch config
 $ gedit config
```

Here you're going to set your keys:

```
 #zerkeizi account
 Host github.com-zerkeizi
 	HostName github.com
 	User git
 	IdentityFile ~/.ssh/my_key

 #company account
 Host github.com-company
 	HostName github.com
 	User git
 	IdentityFile ~/.ssh/company_key
```

Then clone your repo: 

 git clone git@github.com:zerkeizi/somerepo.git

_Is it your [First Commit](#first-commit)?_

Inside it, config your credentials

```
 $ git config user.name "yourname"
 $ git config user.email "respectivemail@mail.com" 
```

You can also have global credentials configured (those will be used if you don't set them inside a git folder as the previous step demonstrate): 

```
 $ git config --global user.name "yourname" 
 $ git config --global user.email "respectivemail@mail.com"
```

## Finally

```
$ git add .
$ git commit -m "your comments"
$ git push
```

<a name="first-commit"</a# First commit

Make sure you already have the repo on your account, and go for:

 git remote add origin git@github.com:Zerkeizi/yourrepo.git
 git push --set-upstream origin master
