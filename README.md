# uni-app-reserve-date
uni-app 日历组件，区间选择  
   
说明：目前测试平台 H5，APP，微信小程序，其他平台理论上支持。   

## 回调函数示例：

``` html
<template>
	<view class="content">
		<reserve-date @changeDay='changeDay' @changeMonth='changeMonth' :startDate='startDate' :price='price' :isNowDate='isNowDate' :disableBefore='disableBefore' :endDate='endDate' :singleElection='singleElection'/>
	</view>
</template>

import reserveDate from '@/components/reserve-date/reserve-date.vue'
export default {
  data() {
    return {
        price: { 
            type: true, 
            data: [] 
        },
        isNowDate: true,
        disableBefore: false,
        endDate: '',
        startDate: '',
        singleElection: false
    }
  },
  mounted() {
    this.changeMonth(['','', 31])
  },
  methods: {
    // 日期改变
    changeDay(date) {
      console.log(date)
    },
    // 月改变
    changeMonth(data) {
      uni.showLoading({
        title: '加载中',
        mask: true
      })
      let price = []
      setTimeout(() => {
        this.price.data = []
        for(let i = 0; i < data[2]; i++) {
            price.push(parseInt(Math.random() * 1000))
        }
        console.log(price)
        this.price.data = price
        uni.hideLoading()
      },1500)
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
| isNowDate | Boolean | 可选 | 默认是否选择日期（禁止日期不会选择） |
| price | Object（{type: 是否显示价格(Boolean), data: 价格(Array)}） | 可选 | 显示框上月末尾和下月开始几天不显示 |
| singleElection | Boolean | 可选（默认false）| true为单选，false为多选 |
---


## 事件说明

| 属性名 | 类型 | 默认值 |
|---|---|---|
| changeDay | function | 选择日期触发（返回对象，日期和价格） |
| changeMonth | function | 切换月触发 (返回数组：[0]为年,[1]为月，[2]为当月多少天) |

---
## 更新历史说明：   
v1.0.3
* 增加单选和切换月方法
*

v1.0.2
* 跳转边距，字体大小
*

v1.0.1
* 添加价格显示，和默认选择当前日

v1.0.0   
* 初次提交   


## 效果图：
![效果图](https://github.com/193335083/uni-app-reserve-date/blob/master/static/imgs/a6646f10-7f07-11e9-82ed-e71b5443f738_1.png?raw=true)
![效果图](https://github.com/193335083/uni-app-reserve-date/blob/master/static/imgs/a6646f10-7f07-11e9-82ed-e71b5443f738_0.png?raw=true)
   
