WeChat SDK for python
==========

A Wechat SDK used by python

注意事项
------------------
1.将在公共平台上创建的token写入settings.py
2.由于腾讯官方限制 只支持80端口


使用说明
------------------
1.验证api:
    Weixin.valid(signature, timestamp, nonce)
    验证成功返回True, 失败返回False

2.处理用户请求:
    1.初始化WeChat对象
        wechat = WeChat(xml_raw_data)

    2.查看请求类型:
        wechat.MsgType
        有text location image三种值  本别代表用户请求消息类型为文本 地理信息 图片

    3.回复信息
        生成xml文本消息
            response_xml = wechat.textResp(content, funcflag=0)
            funcflag为加星标记 1代表加星 0代表不加星
        
        生成图文消息
            1.生成图片信息
            pic_item = WeChat.make_pic(title, description, picUrl, url)

            2.生成图片列表

            3.response_xml = wechat.picResp(itemList, funcflag=0)
        


