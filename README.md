# GitHub测试项目

---

```
{
    "data": {
        "weather": {
            "forecast_date": "2015年2月28日",
            "city_id": "101020100",
            "city_name": "上海",
            "temperature_live": null,
            "temperature_min": 4,
            "temperature_max": 9,
            "temperature_min_2": 4,
            "temperature_max_2": 9,
            "temperature_min_3": 7,
            "temperature_max_3": 13,
            "weather_day": 2,
            "weather_night": 2,
            "weather": "阴",
            "weather_day_2": 1,
            "weather_night_2": 1,
            "weather_2": "多云",
            "weather_day_3": 1,
            "weather_night_3": 7,
            "weather_3": "多云转小雨",
            "index_xc": "不建议",
            "index_xc_flag": 0,
            "driving_remind": "",
            "description": "路面有积水可能会弄脏车辆，不宜洗车。"
        },
        "pm25": {
            "city_name": "上海",
            "publish_time": "2015-03-30T17:00:00.000+0800",
            "aqi": 28,
            "pm25": 12,
            "quality": "优",
            "driving_remind": "",
            "description": "空气质量优，PM2.5浓度12。",
            "index_window_flag": 1
        }
    }
}
```

字段说明

同 *根据城市名称查询天气*


---
+ **根据IP地址查询天气**

| http method | url                   | 描述          |
|-----------  |---------------        |---------------|
| GET         | /weather/ip/{ip}/ | {ip}代表IP地址字符串：例如："116.24.32.6" |

#### 请求参数

| 参数名      | 必选    | 类型与范围        | 说明                   |
|-------------|---------|-------------------|----------------------  |
| last_city_name    | false | String | 上次查询得到的城市名称，用来避免重复查询 |
| last_query_time   | false | String | 上次查询的时间，ISO8601格式，用来避免重复查询 |

#### 返回结果
同 *根据城市名称查询天气*

错误：

HttpStatus=400
```
{
	"code": "WS100000",
	"msg": "IP地址不能为空"
}
```
HttpStatus=404
```
{
	"code": "WS100001",
	"msg": "IP获取城市失败"
}
```