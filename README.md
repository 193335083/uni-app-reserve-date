# uni-app-reserve-date
uni-app 日历组件，区间选择  
   
说明：目前测试平台 H5，APP，微信小程序，其他平台理论上支持。   

## 回调函数示例：

``` html
<reserve-date @change='change' />
   
   
   
import reserveDate from '@/components/reserve-date/reserve-date.vue'
export default {
	data() {
		return {
		}
	},
	methods: {
		change(date) {
			console.log(date)
		}
	},
	components: {
		reserveDate
	}
}
```
---
	 
## reserve-date属性   
   
| 属性名 | 类型 | 默认值 | 说明 |
|---|---|---|---|
| date | String | 可选 | 如2019-5-25 |
| startDate | String | 可选 | 如2019-5-25， 禁止2019-5-24及以前的日期 |
| endDate | String | 可选 | 如2019-5-25， 禁止2019-5-26及以后的日期 |
| disableBefore | Boolean | 可选 | 禁用今天之前的日期 |
| isNowDate | Boolean | 可选 | 是否默认选择传入日期或者当前日期（禁止日期不会选择） |
| price | Object（{type: 是否显示价格(Boolean), data: 价格(Array)}） | 可选 | 显示框上月末尾和下月开始几天不显示 |
---


## 事件说明

| 属性名 | 类型 | 默认值 |
|---|---|---|
| change | function | 选择日期触发 |

---
## 更新历史说明：   
v1.0.2
* 跳转边距，字体大小

v1.0.1
* 添加价格显示，和默认选择当前日

v1.0.0   
* 初次提交   


## 效果图：
![效果图](https://github.com/193335083/uni-app-reserve-date/blob/master/static/imgs/a6646f10-7f07-11e9-82ed-e71b5443f738_1.png?raw=true)
![效果图](https://github.com/193335083/uni-app-reserve-date/blob/master/static/imgs/a6646f10-7f07-11e9-82ed-e71b5443f738_0.png?raw=true)
   
