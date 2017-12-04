# calculate-time
关于时间的各种计算


## 获取今天日期
```angular2html
  function mmDateDay (){
    var t = new Date();
    return t.getFullYear() + '-' + _formatTwo(t.getMonth() + 1) + '-' + _formatTwo(t.getDate())
  };
```


## 计算日期差
```angular2html
  // 计算两个日期之间相差的天数
  function Computation( sDate1, sDate2){
    var aDate, oDate1, oDate2, iDays;
    aDate = sDate1.split("-");
    oDate1 = new Date(aDate[1] + "-" + aDate[2] + '-' + aDate[0])   //转换为12-13-2008格式
    aDate = sDate2.split("-");
    oDate2 = new Date(aDate[1] + '-' + aDate[2] + '-' + aDate[0])
    iDays = parseInt(Math.abs(oDate1 - oDate2) / 1000 / 60 / 60 /24)+1;   //把相差的毫秒数转换为天数
    return iDays-1;
  };
```

## 将时间*12:33:24*转换成秒数
```angularjs
countSeconds(time) {
        debug('teme', time);
        let arr = time.split(':');
        let secs = arr[0] * 3600 + arr[1] * 60 + parseInt(arr[2]);
        return secs;
      };
// countSeconds('12:33:24')
```

## 将秒数转换为时间（超过24小时并未作处理）
```angularjs
secondsToTime(seconds) {
        let h = parseInt(seconds / 3600);
        let m = parseInt(seconds % 3600 / 60);
        let s = seconds % 3600 % 60;
        h = h < 10 ? `0${h}` : h;
        m = m < 10 ? `0${m}` : m;
        s = s < 10 ? `0${s}` : s;
        return `${h}:${m}:${s}`;
      };
// secondsToTime(2342)
```
## 获取时间毫秒数
```angular2html
 new Date().getTime()
 // 1511405087925
```
## 将格林尼治时间转换为标准时间
```angular2html
var time = 2017-12-04T07:25:45.881Z
var change = {{time.split('T')[0]}} {{time.split('T')[1].substring(0,8)}}
console.log('change') // 2017-12-04 07:25:45 
```
