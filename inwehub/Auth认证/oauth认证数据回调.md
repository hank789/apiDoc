# oauth认证数据回调

## 接口地址

`/api/oauth/{type}/callback`

type目前只有:weixinapp|weixin_gzh
## 请求方式

`POST`

### HTTP Status Code

200

## 请求体

| name     | type     | must     | description |
|----------|:--------:|:--------:|:--------:|
| openid | string   | yes   | 唯一标示号 |
| nickname   | string   | yes      | 昵称 |
| avatar     | string   | yes      | 头像 |
| access_token     | int      | yes      | access_token |
| refresh_token | string   | yes      | 用户刷新access_token |
| expires_in | string   | yes   | access_token接口调用凭证超时时间，单位（秒） |
| scope     | string   | yes      | 用户授权的作用域，使用逗号（,）分隔 |
| full_info  | array   | no      | 详细信息 |
| bindType     | int      | yes      | 绑定类型，1无操作，2合并微信账户,默认1 |

## 返回体

```json5
{
  "status": true,
  "code": 1000,//1113：此微信已绑定其它手机号；1131：此微信已注册并可以合并，此时再次调用此接口，bindType传2进行账户合并；1132：当前用户已绑定微信，不能合并微信账户，当bindType为2时触发，正确调用不会出现这类情况
  "message": "操作成功",
  "data": {
    "token": "rfghjk",//登陆凭证，如果返回null，说明未登录
    "wechat_name": "dfd",//微信昵称
    "avatar": "头像",
    "name": "app昵称",
    "is_expert": 1,//是否专家
  }
}
``` 
