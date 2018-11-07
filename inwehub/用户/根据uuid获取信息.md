# 用户个人信息

## 接口地址

`/api/profile/infoByUuid`

## 请求方法

```POST ```

## 接口变量

| name     | type     | must     | description |
|----------|:--------:|:--------:|:--------:|
| uuid | string   | yes      | 用户uuid |


### HTTP Status Code

200

## 返回体

```json5
{
  "status": true,
  "code": 1000,
  "message": "ok",
  "data": {
    "info":{
      "id": 6,
      "name": "hank",
      "mobile": "15050368287",
      "email": "",//电子邮箱
      "avatar_url": "http://zhihu.hank.com:8080/image/avatar/1_middle.jpg",
      "gender": "男,
      "province": ['key'=>'110000','name'=>'北京市'],//工作所在省份
      "city": ['key'=>'110101','name'=>'东城区'],//工作所在城市
      "address_detail": "上海市浦东新区",//详细地址
      "title": null,//身份职业
      "company": "滴滴",//公司
      "industry_tags": [{"value":"5566","text" :"金融"},{"value":"5567","text" :"供应链金融"}],//所在行业
      "skill_tags": [{"value":"5566","text" :"金融"},{"value":"5567","text" :"供应链金融"}],//他的擅长
      "description": null,//个人描述
      "is_expert": "0",//是否专家,0否,1是
      "expert_level": "认证专家",//专家级别
    },
    "is_followed": 0,//是否关注,0未关注,1已关注
  }
}
```

## 返回字段



code请参见[消息对照表](消息对照表.md)