# Cursor_Change_ID_Auto

## 🌟 重要提示

> **目前推荐使用 YCursor，能防掉试用 等其他好用的功能**
>
> **win和mac已经发布**
>
> **Ycursor 文档 [点我](https://docs.qq.com/aio/DV2VKUnNaeFRyRGRH?p=DKRZhtXI98ELAa724va8q8) 👈**





全网免费auto第一个解决自动更换账户后打开Cursor账户自动退出问题

> 本程序由开源脚本思路整合，感谢各位Github以及各大论坛的大佬无私奉献！
>
> 本工具完全免费，不进行任何收费
>
> 获取最新版本请加入QQ群：1051756343

> 不直接发布在Github原因已经很明了，防止被倒卖。国内的开源环境就这样，差得很

## 🚀 最新更新 v7.6.0
- 新增支持 Cursor v0.50.x 版
- 优化界面显示和用户体验
- **解决自动登录后打开Cursor会自动退出问题（超级无敌重要）**
- **重构修改机器码修改更新逻辑使Mac支持更高的版本**
- **优化整体注册速度**
- **新增自动获取UA（无头模式下也可正常获取）**
- **新增浏览器随机指纹（加强）**
- **新增自动清理验证码邮件功能**
- **新增自动登录重试获取令牌功能（新）**
- **新增支持 tempmail.plus 临时邮箱（配置更简单）**
- **新增终端询问自动选择配置（懒人必备，连回车都不用按了）**
- **新增获取的账号信息保存到本地（配合YCursor可实现管理账号本地账户池使用）**
- 新增自定义正则表达式（查找验证码时）
- 改进邮箱验证码获取逻辑
- 增强系统稳定性和兼容性
- 修复已知问题和bug

## 📋 功能特性
1. **自动注册功能**
   - 自动生成随机账号信息
   - 自定义邮箱域名
   - 浏览器随机指纹
   - 自动获取UA
   - 自动处理人机验证
   - 自动获取验证码
   - 自动清理验证码邮件
   - 自动替换旧账户
2. **ID修改功能**
   - 支持自动修改机器码
   - 自动备份原有配置
   - 支持禁用自动更新
   - 兼容多系统平台
3. **邮箱支持**
   - 支持 临时邮箱 收件配置
   - 支持 IMAP 邮箱收件配置
   - 多种邮箱收件方式

## 💻 使用要求
- Windows/macOS 系统
- 已安装 Cursor 并且安装在默认路径下（不在可以重装）
- 已安装 Google Chrome 浏览器并且安装在默认路径下（不在可以重装）
- 稳定的网络连接（不稳定可以挂🪜）

## ⚙️ 配置说明
1. **环境配置**

   - 确保已安装 Chrome 浏览器
   - 确保系统时间正确
   - 确保网络连接稳定

2. **.env 文件配置(不使用自动注册可以不用配置)**

   > 不用在这里复制，运行脚本会自动生成.env

   ```ini
   # 不用在这里复制，运行脚本自动生成！
   
   # 代理（仅在自动注册时有效）
   # BROWSER_PROXY='http://127.0.0.1:2080' 
   
   # Cloudflare 域名邮箱地址 (必填)
   # 需要把自己的域名托管到 Cloudflare 并且设置邮件路由规则
   DOMAIN=xxxxx.com 
   
   # 临时邮箱配置（可选必填，与IMAP二选一）
   # 使用 tempmail.plus 临时邮箱服务
   TEMP_MAIL=your_full_email@mailto.plus      # 临时邮箱完整地址
   TEMP_MAIL_EPIN=your_epin_code              # 临时邮箱PIN码
   
   # IMAP邮箱配置（可选必填，与临时邮箱二选一）
   # 不再支持163邮箱，请使用其他邮箱
   # 推荐使用QQ邮箱
   # IMAP_SERVER=imap.qq.com    # [必填] IMAP服务器地址
   # IMAP_PORT=993              # [必填] IMAP端口，SSL通常为993
   # IMAP_USER=xxx@qq.com       # [必填] 邮箱地址
   # IMAP_PASS=xxx              # [必填] 邮箱授权码或密码
   # IMAP_DIR=                  # [可选] 默认为收件箱(inbox)
   
   # 无头模式
   # BROWSER_HEADLESS='True'    # True为启用 False为不启用
   # 当开启无头模式时，如果发现无法自动获取User-Agent，那么就需要配置浏览器User-Agent，否则无法过人机
   # BROWSER_USER_AGENT=your_browser_user_agent         # 浏览器User-Agent
   
   # 验证设置
   TURNSTILE_TIMEOUT=20     # Turnstile 验证超时时间（秒）
   VERIFICATION_CODE_TIMEOUT=180  # 验证码邮件有效期（秒），默认3分钟
   
   # 是否自动清理所有 Cursor 邮件（避免堆积太多验证码邮件）
   # 使用临时邮箱的推荐启用
   CLEAN_ALL_CURSOR_MAILS='False'  # True为启用 False为不启用
   
   # 验证码正则表达式配置（可选）
   # 注意：在.env文件中配置正则表达式时，所有特殊字符如\b \d等必须使用双反斜杠(\\)表示
   # 例如：\b写成\\b, \d写成\\d, 否则将导致正则表达式无法正确解析
   # VERIFICATION_CODE_PATTERN="\\b\\d{6}\\b"              # IMAP邮箱验证码匹配规则，默认匹配6位数字
   # TEMP_MAIL_CODE_PATTERN="(?<![a-zA-Z@.])\\b\\d{6}\\b" # 临时邮箱验证码匹配规则，默认匹配不紧跟在字母或域名符号后的6位数字
   
   # 终端询问自动选择配置（启用对应的配置后终端不在询问，而是通过你配置的进行自动选择）
   # DEFAULTACTION=3                 # 1.仅修改ID | 2.仅进行注册流程 | 3.执行全流程（修改ID+注册）
   # MODIFYUPDATE=N                  # 是否禁用自动更新？(Y/N)
   # AUTOREGISTERCURSORACCOUNT=Y     # 是否自动注册Cursor账号？(Y/N) 
   
   # 调试配置
   # SHOW_VERIFICATION_EMAIL_CONTENT='True'  # 是否显示验证码邮件的完整内容
   ```

## 🚀 使用说明

### Windows

```
右击 Yan_cursor_Change_ID_Auto.exe，使用管理员权限运行  # 7.0.0往后版本可双击运行，会自动提权
```



###  Mac

解压压缩包获取脚本

```
# 先给可执行权限
chmod +x Yan_cursor_Change_ID_Auto
# 使用管理员权限运行
sudo ./Yan_cursor_Change_ID_Auto
```
>  你的CPU是ARM也就是苹果的CPU的请使用ARM版本，Intel的请使用X86-64版本
>
>  QQ群公告查看更详细的启动教程

1. **首次使用**
   - 运行程序会自动创建 .env 文件
   - 请按照.env里的注释配置
   - 确保.env里所有配置填写是正确的
2. **注册流程**
   - 获取UA，并且随机生成浏览器指纹
   - 程序会自动生成随机账号
   - 自动填写注册信息
   - 自动处理验证码
   - 完成注册后会自动替换旧账号
3. **ID修改**
   - 自动备份原有配置
   - 生成新的机器码
   - 更新系统配置
   - 禁用自动更新

## ❗ 常见问题
1. **验证码获取失败**
   - 检查邮箱配置是否正确
   - 确认网络连接是否稳定
   - 尝试更换QQ邮箱或其他稳定的邮箱
2. **浏览器相关问题**
   - 确保 Chrome 浏览器已正确安装
   - 检查浏览器版本是否兼容
   - 尝试更新浏览器版本
   - 有谷歌浏览器还报错可以尝试重装谷歌浏览器
3. **注册失败问题** [推荐节点18.9 1000G 无限时高速节点（需要梯子打开）[点我购买]](https://赔钱机场.com/#/register?code=eQhqGLmx)
   - 检查网络连接
   - 确认配置文件正确
   - 查看错误提示信息
4. **人机验证过不去** [ 推荐节点18.9 1000G 无限时高速节点（需要梯子打开）[点我购买]](https://赔钱机场.com/#/register?code=eQhqGLmx)
   - 检查网络环境手动注册是否能过去
   - 更换网络环境
   - 开启或关闭代理以及更换节点
5. **注册受到限制** [推荐节点18.9 1000G 无限时高速节点（需要梯子打开）[点我购买]](https://赔钱机场.com/#/register?code=eQhqGLmx)
   - 检查网络环境手动注册是否能过去
   - 更换网络环境
   - 开启或关闭代理以及更换节点
   - 使用群里的geek删除谷歌浏览器，在用群里的谷歌浏览器安装器重新安装谷歌浏览器


## ✅新功能已经解决的问题

1. **随机浏览器指纹** （解决`注册受到限制`和`身份认证被阻止`）
   ![](./img/0b5eeafc3fa8feb57fe04516abd52459.png)

   ![](./img/7dc6c2dd748d307e6885bb0fdccbec51.png)

2. **自定义UA** （解决`人机认证过不去问题`）
   ![](./img/3ad2bf842a3758a2da24126398bbdc76.jpg)

3. **自动登录重试获取令牌**（解决`自动注册令牌获取失败，导致自动替换旧账户失败`）
   ![](./img/922a42c26da7f6c5faa5b246f87c2526.png)


## 🔒 安全提示
- 请勿将.env配置文件分享给他人
- 妥善保管注册的账号信息

## 🆘 获取帮助
- 遇到问题请加入QQ群：631250950
- 获取最新版本请加群下载
- 技术支持请联系群主
- 提供详细的错误信息和截图

## 📝 免责声明
1. 本工具仅供学习和研究使用
2. 请勿用于任何商业用途
3. 使用本工具所产生的一切后果由使用者自行承担
4. 如有侵权请联系我们删除

## 🎯 更新计划
- [x] 额度查询
- [x] 本地切换账号
- [x] 本地管理账号

你还有其他更好的想法吗？

## 💌 联系方式
- QQ群：1051756343
- 获取最新版本请加群下载
- 技术交流请加群联系群主

## 🎁 打赏与交流
> 如果觉得工具好用，可以请作者喝杯咖啡，同时加入QQ群获取更多技术支持！

| 微信收款码 | 支付宝收款码 | QQ群邀请码（1051756343） |
|:---------:|:-----------:|:---------:|
| ![微信](./img/wx.png) | ![支付宝](./img/zfb.jpg) | ![QQ群](./img/qq2.jpg) |
| 微信打赏 | 支付宝打赏 | QQ群：1051756343 |

## ⭐ 特别说明
1. 本工具完全免费，谨防受骗
2. 定期关注更新，及时获取新功能
3. 欢迎加群交流使用心得
4. 感谢大家的支持和反馈
5. [推荐节点18.9 1000G 无限时高速节点（需要梯子打开）[点我购买]](https://赔钱机场.com/#/register?code=eQhqGLmx)

## ❤ 感谢

Journey - 提供的自动化思路

煎饼果子卷鲨鱼辣椒 - 提供的修改机器码思路

群友 @atom - 提供的帮助

---
**文档最后更新时间：2025-05-25 2:00**

**脚本更新在群里通知，上面只是文档**

_如果觉得好用，请推荐给身边的朋友，一起加入QQ群：1051756343