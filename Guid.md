###今天分享一下工作中常用到的  如何生成一个随机的Guid值
###生成一个随机的Guid值 方法如下：
```
function newGuid(){
     var guid = "";
     for (var i = 1; i <= 32; i++){
         var n = Math.floor(Math.random()*16.0).toString(16);
         guid +=   n;
         if((i==8)||(i==12)||(i==16)||(i==20))
             guid += "-";
     }
     return guid;
 }
 ```
###然后调用一下这个newGuid（），就可以得到一个随机的Guid值

###有时候可以通过cookie 存储一下 可以拿到唯一的id
```
var appid = $.cookie("liuda");
if(appid === null){
  appid = newGuid();
  $.cookie("liuda",appid);	
}
```
###这样appid最终拿到的是唯一的。