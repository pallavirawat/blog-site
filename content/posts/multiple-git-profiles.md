---
title: "Managing Multiple Git Profiles"
date: 2021-09-11T21:24:39+05:30
draft: false
tags: ["git","tech"]
categories: ["git","tech"]
description: "how to maintain multiple git profiles without much hassle"
---

<br/><br/>
Personally I really like to organise things especially profiles that I can maintain when I am using same laptop for
personal and work repositories.<br/>
No one wants to commit on a work repo with their private personal email. So you can either change that setting at repo level 
or just have flexible config which is smart to use the right config with the right repository.<br/>
There are definitely multiple ways to get this done.
The one that I use is via multiple git configs. It is neat and easier to create more profiles.
Let's jump onto this...

<br/>

### Lets cover some Basics first
For any git config, git usually looks first in `[path]/etc/gitconfig` file which is system wide i.e for all users
in the system. It then looks into `~/.gitconfig (or ~/.config/git/config) ` which is user specific.
I usually make changes into user specific only. But depending on your need you can also make changes acordingly.
For simplicity consider the below steps are for user specific changes only but you can extend them if needed for system wide.
More [here](~/.gitconfig (or ~/.config/git/config) )

<br/>

### Over to the main task
Time to create multiple gitconfigs now.<br/>
Lets say we want to create 2 profiles one for work and one personal

So we will go ahead and create two gitconfigs as follows into our home directory
```bash
#config-1 : this is for personal work
touch ~/.gitconfig-personal

#config-2 : this is for official work
touch ~/.gitconfig-work
```

<br/>
Usually we would want our name and email id separate for sure for these two profiles.
So lets go ahead and put it into these two config files

For **gitconfig-personal**
```bash
[user]
	name = coder bill
	email = bill-personal@example.com
```
<br/>

For **gitconfig-work**
```bash
[user]
	name = Bill Saga
	email = bill-working@example.com
```

You can put anything here, whatever git config you only want to use for a particular profile
>For list of various git configs options see [here](https://git-scm.com/docs/git-config)

<br/>

Over to the most important work, I would like to tell my git to use these configs whenever I am in a particular repo/directory.
We will go ahead and add this config into our main **~/gitconfig** file which is what git is aware of by default.
```
[includeIf "gitdir:/Users/bill/PersonalProjects/**"]
    path = ./.gitconfig-personal

[includeIf "gitdir:/Users/bill/MyCompanyProjects/**"]
    path = ./.gitconfig-work
```

<br/><br/>
That's it :rocket:
No need to change config everytime for every repo separately. 
No more embarrassing mistakes of using wrong configs for wrong repo.






