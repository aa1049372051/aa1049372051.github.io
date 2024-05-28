GitLab添加SSH密钥，拉取代码操作流程
下载安装Git工具
https://git-scm.com/downloads 打开链接，根据自己的操作系统下载安装包
安装过程，全保持默认设置即可。

获取公钥
在本机找一个目录存放即将要拉下来的代码。下面以`F:\Git`为例

Windows用户，通过右键菜单中的“Git Bash Here”打开命令行。
Mac OS用户打开本机的“终端”来打开命令行。其它的操作是一样的。

下面以Windows用户界面为例



先确认一下本机中是否有.ssh目录
执行ls ~/.ssh命令
如果像下面一样提示
“ls: cannot access '/c/Users/Administrator/.ssh': No such file or directory”
 ls ~/.ssh
ls: cannot access '/c/Users/Administrator/.ssh': No such file or directory


则表示当前用户目录下没有.ssh这个目录，需要创建。
创建命令
mkdir ~/.ssh


如果没有错误提示则表示该目录已经存在，不用创建。检查一下是否有一个名为“id_rsa”的文件，避免本机已经存在密钥而新创建的密钥将其覆盖掉。
ls ~/.ssh/id_rsa


如果有
则跳过创建步骤，直接跳转到 查看本机私钥对应的公钥内容 

如果没有
则手动创建密钥对。执行如下命令，所有输入选项直接回车即可。过程类似下面显示
# ssh-keygen -t rsa
# 只执行上面的命令，下面是提示信息，不用输入命令行。
 Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/Administrator/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/Administrator/.ssh/id_rsa
Your public key has been saved in /c/Users/Administrator/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:Z18zLkfJsBzLvxPmB9PCW4T2V5lYs527UethyHUpWJw Administrator@PC-20160523KWSZ
The key's randomart image is:
+---[RSA 3072]----+
|            . .  |
|             E o |
|            = o.O|
|           + OoO*|
|        S o *o@+*|
|         o . BBO=|
|            oo*B=|
|             o++.|
|              .o |
+----[SHA256]-----+



查看本机私钥对应的公钥内容
执行ssh-keygen -y -f ~/.ssh/id_rsa 
# ssh-keygen -y -f ~/.ssh/id_rsa
# 只执行上面的命令，下面是显示信息，不用输入命令行。
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDU+rD2UlCAkF6mpLaZ3Wknnw0APMouSiwqpXvkBzVNDn7qKQvz47foP0CcRYX4aQCDtGu4Bk2CvX2zw9vJBb6M2F1yCYM6Jl6Bhd+oHnJZSI6EfoQrPy5/VgIFhFXsytVn6vhyThdyZbtf+4kl/prStGKE4qO/ATrB0FXeqcm4yAbD+ZL8VPJsTQRJpJCrbq/XOekTwQbFDrewl4OzPgFhV9RoYjNZjjjd1vgtDZW2OyXGDhdEDKYq/P2GF39CDfH//KwZku9Iq9vYSYhseaSY/gN3G5xm46mXscHQDV3tG/b5v5/2ZGb6xnQhWMFFArqGCR1Fopxyy+Xl3kL5qjNGpAQr7Bbtp5+D3GkykCn09fUXUtP/bgi2Btyjz5/qJmUVjysgoea6+B6BdEMK5uEmdAdqm4LNGguJQXGAs8/wio5ZTHk+O49VThQExn6tc3TwvokITLRrnnoKZzhFVHoLZUvdlT8LI3gnaz4rrFxa/9bMZgnTUoIi9ll54dO+zS0= 




登录GitLab
打开Sign in · GitLab链接登录至GitLab。如果不知道自己的用户信息，请查看邮件是否有创建用户的邮件通知（该邮件由运维创建用户时，GitLab自动发送）。如果邮件中没有，请联系运维添加账号。

绑定双重认证
首次登录时看到如下提示。是因为WEB登录默认开启了两步验证。需要绑定一个动态验证码生成器才能继续使用。 
可以在手机应用商店下载 “Microsoft Authenticator”。
安卓手机如果在本机应用商店没有找到，可以通过后面这个链接下载安装。
安装完成后用Microsoft Authenticator进行扫码，然后在下面的密码框输入用户密码，第二个验证码框输入Microsoft Authenticator中显示的动态验证码。最后点“使用双重认证应用注册”即可。


配置GitLab 的 SSH密钥
在左边用户图标处点击，选择进入“编辑个人资料” 



在左侧边栏选择“SSH密钥”，进入后点右侧的“添加新密钥”



将前面在命令行看到的类似的ssh-rsa开头的内容添加到git页面的密钥框中。
并去掉“到期时间”限制。避免到期导致密钥不可用。


然后点击“添加密钥”


拉取代码到本地
点击左上角的图标回到主页




在左侧边栏点击“群组”。进到自己的群组中的对应项目。


这里以81gw项目为例，点击页面右边的蓝色“代码”按钮，点击“使用SSH克隆”地址旁边的复制按钮，将仓库路径复制下来。



将复制的仓库路径返回到命令行中执行如下类似命令进行拉取代码。
git clone ssh://git@git.whkht.com:2222/php/81gw.git


命令结束即可在本地查看代码。


