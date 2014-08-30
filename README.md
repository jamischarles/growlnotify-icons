#Growlnotify-icons
Helps you display growl message with fancy icons after certain terminal commands like `npm install`.



## Get started
1) Install [growlnotify](http://growl.info/downloads)

2) Put this in a .bashrc or .zshrc file.
``` bash
# --app param tells growl what apps' icon to use.
growl () { echo $1 | growlnotify --title $2 --app iterm -m $1 } #requires growlnotify

# params: $1 title  $2 msg  $3 imageName
growlImg () { echo $2 | growlnotify --image ~/github/growlnotify-icons/images/$3  -t $1 -m $2 }
```

3) Now you can either
- Run `growl` from terminal if you don't care about the icons. OR
- Run `growlImg` from the terminal for messages and icons.  OR  
- Add aliases like the following to your .bashrc or .zshrc file:

``` bash
# aliases 'git pull', and then sends a growl notification.
alias gp="git pull --rebase origin master;  growlImg 'Git Pull' ' ' github.png"
```

Now, when you run `gp` from the terminal, you get a growl notice when you're done.

## Triggers
As a bonus, use [iTerm](https://iterm2.com/), and set custom triggers.
This allows custom growl notices based on any regex in the terminal.

So your app takes a long time to start? Set a regex for `Listening on` and you get a growl notice
when that action happens. Pretty powerful.

Here's how you get it set up:  
- iTerm -> Preferences -> Advanced -> Triggers
- `Regex: Listening on`
- `Action: Send Growl Alert`
- `Parameters: App has started!`

Modify the text you're looking for (Regex)  and the growl message (Parameters)

## Image Credit / Sources:  
Github Icons https://octicons.github.com/  
NPM badges https://nodei.co/
