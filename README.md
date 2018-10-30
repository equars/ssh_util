#インストールと使用法  
自分のローカルにいながらssh接続先のディレクトリやファイルをタブ補完できる，scpやlsの強化版です．
.bash\_completionファイルを自分のホームディレクトリに置き，.bashrcを下の英語版の説明のようにします．
ターミナルを再起動するか，bashrcを読み込んで使用します．
できる限りsshは公開鍵認証に，ssh接続情報はconfigに設定しておくと便利です．
sscpならscp，slsならlsと使用方法や機能は同じです（エイリアス設定をみれば当然ですね．）
scpなら`$scp hoge:~/foo/bar.txt ~/dir1/`のように使用すると思いますが，sscpならばhoge:に続くリモート側のディレクトリにもTabキーによる補完が可能です．

#注意  
まだ完全に使えるわけではありません．
ディレクトリやファイルのいかんに関わらず補完後にカーソルとワードの間に空白が入ってしまうなどの問題があります．
複数回の補完は不便ですが１字戻って使用してください．  
slsは現在使えないものと考えてください．

#English  
Commands "scp" and "ls" with the function of completion directory name.
Auto completion as usual on your local.

##How to install.  
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

##How to use.  
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
    $sscp /usr/loc<tab>
  ```
  ```
    $sscp /usr/loccal
  ```
  but this event is exactly(?) same as "scp".
  Then, we'll try it.
  ```
    $sscp myPC:/usr/loc<tab>
  ```
  ```
    $sscp myPC:/usr/local
  ```
  Automatically seek server directory even if you are on local.

##Caution.  
Temporally disavailabe "sls" command.

