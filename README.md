# 新版正方教务教务系统API

**因为学校账号有限，如果有和自己学校系统不适配的地方，请提issues，我都会尽量解决。对于抢课和评价功能，如果有朋友的学校正在抢课或者评论，能提供自己的账号帮助项目的，可以将其发在我git主页的邮箱里，万分感谢🙏**

更多内容可以访问项目主页：

> [正方教务管理系统API](https://neroasmar.top/zfnew/)

一个有关新版正方教务管理系统（如下图展示的主页面即为新版教务系统）的API，可以实现教务系统内基础的查询功能，未来还会添加选课抢课，一键评价等功能。
![主页](doc/image/main_page.png)

## 已实现与待实现
* [x] 自动登陆、cookies获取
* [x] 个人信息
* [x] 学校通知
* [x] 调课、改课消息
* [x] 成绩
* [x] 课程表
* [x] 考试信息
* [ ] 自动抢课
* [ ] 一键评价
* [ ] 选课名单
* [ ] 实验考试
* [ ] 选课名单

## 如何开始
1. 使用pip命令安装 `set PYTHONUTF8=1` & `pip install zfnew`

2. 在[Pypi](https://pypi.org/project/zfnew/#files)下载包文件，然后

   ```bash
   tar -zxvf 包名.tar.gz
   cd 包名
   python setup.py build
   python setup.py install
   ```

接着在python中运行如下代码验证：
```python
from zfnew import *

base_url = '学校教务系统的主页url'

lgn = Login(base_url=base_url)
lgn.login('账号', '密码')
cookies = lgn.cookies  # cookiejar类cookies获取方法
person = GetInfo(base_url=base_url, cookies=cookies)
print(person.get_pinfo())

```
如果能输出json形式的个人信息，说明运行成功。

## 详细API介绍
**推荐直接结合调用例子：** [examples](https://github.com/NeroAsmarr/zfnew/tree/master/examples)
