# Cursor_Change_ID_Auto

## 🌟 重要提示
> 本工具完全免费，如果你是付费购买的，那么你已经被骗了！
>
> 获取最新版本请加入QQ群：631250950

> 不直接发布在Github原因已经很明了，防止被倒卖。国内的开源环境就这样，差得很

## 🚀 最新更新 v5.1.0
- 新增支持 Cursor v0.45.x 版本
- 优化界面显示和用户体验
- **优化整体注册速度**
- **新增自动获取UA**
- **新增浏览器随机指纹**
- **新增自动清理验证码邮件功能**
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
   
2. **ID修改功能**
   - 支持自动修改机器码
   - 自动备份原有配置
   - 支持禁用自动更新
   - 兼容多系统平台

3. **邮箱支持**
   - 支持 IMAP 邮箱配置
   - 支持临时邮箱(tempmail.plus)
   - 支持自定义域名邮箱
   - 多种邮箱验证方式

## 💻 系统要求
- Windows/macOS/Linux 系统
- 已安装 Google Chrome 浏览器
- 稳定的网络连接

## ⚙️ 配置说明
1. **环境配置**
   - 确保已安装 Chrome 浏览器
   - 确保系统时间正确
   - 确保网络连接稳定

2. **.env 文件配置(不使用自动注册可以不用配置)**
   
   ```ini
   # 代理 一般不需要，如果需要请使用软件的代理
   # BROWSER_PROXY='http://127.0.0.1:2080' 
   
   # 无头模式
   BROWSER_HEADLESS='False' # True False
   
   # 页面加载配置
   # PAGE_LOAD_TIMEOUT=30  # 页面加载超时时间（秒） 防止页面加载过慢导致程序卡死
   # WAIT_BEFORE_VERIFY=5  # 等待验证码输入时间（秒） 确保页面元素完全加载，提高验证成功率
   TURNSTILE_TIMEOUT=20  # Turnstile 验证超时时间（秒）
   
   # 验证码邮件有效期（秒）
   VERIFICATION_CODE_TIMEOUT=180 # 默认3分钟，如果网络较慢可以适当增加
   
   # 是否自动清理所有 Cursor 邮件（避免堆积太多验证码邮件）
   CLEAN_ALL_CURSOR_MAILS='True'  # True False
   
   # Cloudflare 域名邮箱地址 需要设置邮件路由规则(必填)
   DOMAIN=xxxxx.com 
   
   # （必填二选一）
   # 临时邮箱地址https://tempmail.plus/zh/#!
   # TEMP_MAIL='xxxxxx'   # tempmail.plus 生成的临时邮箱地址 
   #   -如你临时邮箱为：abc@tempmail.plus，就填TEMP_MAIL='abc'就好 
   #
   # 当为TEMP_MAIL='xxxxxx'时，会使用tempmail.plus的邮箱收件箱
   # 当为TEMP_MAIL=null时，会使用下面邮箱设置的邮箱的收件箱
   #
   # 两个只能选择一个，推荐自己配置IMAP邮箱，更稳定
   TEMP_MAIL=null
   
   # IMAP服务器配置(TEMP_MAIL为null时必填)
   # 推荐使用QQ邮箱
   IMAP_SERVER=imap.qq.com    # IMAP电子邮件服务器主机名
   IMAP_PORT=993               # IMAP端口，SSL通常为993
   IMAP_USER=xxx@qq.com        # 电子邮件地址
   IMAP_PASS=xxx               # 电子邮件密码或授权码
   # IMAP_DIR=                 # [可选] 默认为收件箱(inbox)
   ```

## 🚀 使用说明

### Windows

```
右击 Yan_cursor_Change_ID_Auto.exe，使用管理员权限运行
```



### Linux / Mac

```
sudo ./Yan_cursor_Change_ID_Auto

或者使用root用户执行脚本
```
>  mac用户你的CPU是ARM也就是苹果的CPU的请使用ARM版本，Intel的请使用X86-64版本

1. **首次使用**
   - 运行程序会自动创建 .env 文件
   - 按照提示配置邮箱信息
   - 确保所有配置正确填写
2. **注册流程**
   - 获取UA，并且随机生成浏览器指纹
   - 程序会自动生成随机账号
   - 自动填写注册信息
   - 自动处理验证码
   - 完成注册后显示账号信息
3. **ID修改**
   - 自动备份原有配置
   - 生成新的机器码
   - 更新系统配置
   - 禁用自动更新

## ❗ 常见问题
1. **验证码获取失败**
   - 检查邮箱配置是否正确
   - 确认网络连接是否稳定
   - 尝试更换邮箱或配置方式
2. **浏览器相关问题**
   - 确保 Chrome 浏览器已正确安装
   - 检查浏览器版本是否兼容
   - 尝试更新浏览器版本
3. **注册失败问题**
   - 检查网络连接
   - 确认配置文件正确
   - 查看错误提示信息
4. **人机验证过不去**
   - 检查网络环境手动注册是否能过去
   - 更换网络环境
   - 开启或关闭代理以及更换节点
5. **注册受到限制**
   - 检查网络环境手动注册是否能过去
   - 更换网络环境
   - 开启或关闭代理以及更换节点


## ✅目前已经解决的问题

1. 注册受到限制和身份认证被阻止（已解决随机浏览器指纹），但不包括你的网络环境有问题！
   1. ![](./img/0b5eeafc3fa8feb57fe04516abd52459.png)
   2. ![](./img/7dc6c2dd748d307e6885bb0fdccbec51.png)
2. 人机认证过不去（已解决自定义UA），但不包括你的网络环境有问题！
   1. ![](./img/3ad2bf842a3758a2da24126398bbdc76.jpg)

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
- [ ] 添加获取失败token后启用自动登录，然后再获取一次

## 💌 联系方式
- QQ群：631250950（推荐）
- 获取最新版本请加群下载
- 技术交流请加群联系群主

## 🎁 打赏与交流
> 如果觉得工具好用，可以请作者喝杯咖啡，同时加入QQ群获取更多技术支持！

| 微信收款码 | 支付宝收款码 | QQ群邀请码 |
|:---------:|:-----------:|:---------:|
| ![微信](./img/wx.png) | ![支付宝](./img/zfb.jpg) | ![QQ群](./img/qq.jpg) |
| 微信打赏 | 支付宝打赏 | QQ群：631250950 |

## ⭐ 特别说明
1. 本工具完全免费，谨防受骗
2. 定期关注更新，及时获取新功能
3. 欢迎加群交流使用心得
4. 感谢大家的支持和反馈

---
**文档最后更新时间：2025-02-09 18:00**

**脚本更新在群里通知，上面只是文档**

_如果觉得好用，请推荐给身边的朋友，一起加入QQ群：631250950_ 