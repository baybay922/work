<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1, maximum-scale=1">
	<title>Document</title>
	<style>
		*{margin: 0;padding: 0;list-style: none;}
		header{width: 100%;height: 3rem;}
		.city_list{display: -webkit-box;height: 3rem;line-height: 3rem;border-bottom: 1px solid #ccc;}
		.city_list li{width: 33.3%;text-align: center;position: absolute;background: #fff;}
	</style>
</head>
<body>
	<header>
		<ul class="city_list" id="city_list">
			<li>选择省</li>
			<li>选择市</li>
			<li>选择区</li>
		</ul>
	</header>
	<script src="http://m.caifupad.com/js/jquery-1.8.3.min.js"></script>
	<script>
		;(function(window, undefined){
			/*$.fn = $.prototype = {
				constructor: $,
				ready : function(){
					alert("1")
				}
			}*/

			$.object = {
				ready:function(){
					$.object.Indexes($("#city_list"));
				},
				getParameter: function(getUrl){
					getUrl?getUrl:$.object.Dialog("请输入URL内容");
						var reg = new RegExp("(^|&)" + name + "=([^&]*)(&|$)"); //构造一个含有目标参数的正则表达式对象
			            var r = window.location.search.substr(1).match(reg);  //匹配目标参数
			            if (r != null) return unescape(r[2]); return null; //返回参数值
				},
				Dialog : function(content){
					alert(content)
				},
				Indexes : function(city_list){
					city_list.find("li").css({
						"index":1
					})
					for(var i = 0; i <= city_list.find("li").length-1; i++){
						console.log(city_list.find("li"))
						city_list.find("li").css({
							"index":-i
						})
					}
					//$("#city_list li").css("index":)
				}
			}
			//console.log($.object.getParameter())
			$.object.ready();
		})(window, undefined);
	</script>
</body>
</html>
