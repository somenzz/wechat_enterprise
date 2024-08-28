# 用 Python 发送企业微信消息

支持发送：
- 文本
- 文件
- 图片
- MarkDown

## 安装
```sh
pip install wechat-enterprise-sdk
```

## 使用

获取的 access_token 会保存在 ./tmp/cache.json 里面，避免高频率获取 access_token。

```python
from wechat_enterprise import WechatEnterprise
we = WechatEnterprise(
    corpid="ww2563f***********",  # 企业 ID
    appid="100****3",  # 企业应用 ID
    corpsecret="*********************",  # 企业应用 Secret
)

#接收者 ID，在企业微信通讯录中查看
receivers = ["ZhengZheng", "DaZhengGe"]
# 发送 文本
we.send_text("来息 somenzz 的消息", receivers)
# 发送 Markdown
we.send_markdown("# Markdown", receivers)
# 发送图片
we.send_image("/Users/aaron/Downloads/images.jpeg", receivers)
# 发送文件
we.send_file("./wechat_enterprise.py", receivers)
# 根据手机号获取企业微信账号：
userid = we.get_userid("138********")
we.send_text("hello",[userid,])
```

## todo

添加企业微信的其他实用功能

## 联系我

添加微信 「somenzz-enjoy」 备注 「github」

个人公众号 「Python七号」，微信搜一搜关注。
