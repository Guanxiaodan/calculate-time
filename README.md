# calculate-time
关于时间的各种计算


## 获取今天日期
```angular2html
  function mmDateDay (){
    var t = new Date();
    return t.getFullYear() + '-' + _formatTwo(t.getMonth() + 1) + '-' + _formatTwo(t.getDate())
  };
```


## 计算时间差
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
