<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>基础JS代码编写2</title>
  </head>
<body>

  <h3>污染城市列表</h3>
  <ul id="aqi-list">
<!--   
    <li>第一名：福州（样例），10</li>
  	<li>第二名：福州（样例），10</li> -->
  </ul>

<script type="text/javascript">

var aqiData = [
  ["北京", 90],
  ["上海", 50],
  ["福州", 10],
  ["广州", 50],
  ["成都", 90],
  ["西安", 100]
];
var olist=document.getElementById("aqi-list");
var oArr=[];
var oMc=["一","二","三","四","五","六"];
var oStr="";
/*(function () {

  /*
  在注释下方编写代码
  遍历读取aqiData中各个城市的数据
  将空气质量指数大于60的城市显示到aqi-list的列表中

//遍历数组，先将大于60的城市挑出来
function oCity(city,code){
	this.city=city;
	this.code=code;
}
   for(var i=0;i<aqiData.length;i++){
       if(aqiData[i][1]>60){
		   //变成对象形式放入数组，方便查询，然后进行排序
	      oArr.push(new oCity(aqiData[i][0],aqiData[i][1]));
	   }
   }
   oArr.sort(function(a,b){return b.code-a.code});
   for(var j=0;j<oArr.length;j++){
      oStr += "<li>"+"第"+oMc[j]+"名的城市是"+oArr[j].city+",得分是"+oArr[j].code+"</li>";
   }
   olist.innerHTML=oStr;
})();*/




 (function () {
        /*
         在注释下方编写代码
         遍历读取aqiData中各个城市的数据
         将空气质量指数大于60的城市显示到aqi-list的列表中
         */
        var str="";
        var pos=["一","二","三","四","五","六"];
        var outputData=aqiData.filter(function(value){
            return value[1]>60;
        }).sort(function(a,b){
            return b[1]-a[1];
        });
        outputData.forEach(function(value,index){
            str+="<li>第"+pos[index]+"名："+value[0]+"，"+value[1]+"</li>";
        });
        document.getElementById("aqi-list").innerHTML=str;
    })();

</script>
</body>
</html>
