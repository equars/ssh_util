Commands "scp" and "ls" with the function of completion directory name.
Auto completion as usual on your local.

#How to install.
1.Put the main file ".bash\_completion" at your home(~/).

2.Then,add lines below with ".bashrc".
  ``` 
  #====This lines about ssh util====
  alias sscp="scp"
  alias sls="ls"
  source ~/.bash_completion
  #=================================
  ```

3.Restart bash or operate "$source .bashrc"

4.enjoy!

#How to use.
Before you will use this, we do recommend you use ssh with public key auth.
And, we also ask you to set "config" file in "{HOME}/.ssh/" if possible. 
How to setting can be found on Google.
The formulas of sscp and sls are same as scp and ls.
Demo are shown below:
1.For example, config file of ssh is like that shown below.
    ```
    Host myPC
        HostName 00.000.000.0
        Port 22
        User user1
    ```
  Namely, you can connect your sever with the command line "ssh myPC"

2.Completion can be atuated when type the tab key.
    ```  
    $sls /usr/loc<tab>
    ```
    ```
    $sls /usr/loccal
    ```
  but this event is exactly(?) same as "scp".
  Then, we'll try it.
    ```
    $sls myPC:/usr/loc<tab>
    ```
    ```
    $sls myPC:/usr/local
    ```
  Automatically seek server directory even if you are on local.

#Caution.

#

