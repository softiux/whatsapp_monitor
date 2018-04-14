# whatsapp_monitor

var jq = document.createElement('script');
jq.src = "https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js";
document.getElementsByTagName('head')[0].appendChild(jq);
$.noConflict();

setInterval(function() {
  //softiux
	var name = $('#main header span').eq(1).text();
	//console.log(name);
	var lastSeen = $('#main header span').eq(2).text();
	//console.log(lastSeen);

	var data = Math.floor(Date.now() / 1000) + "|" + name + "|" + lastSeen
	console.log(data);
	
	var encode = encodeURIComponent(data);
	console.log(encode);
	
	var url = "http://localhost/monitor_wa/save/" + encode;
	console.log(url);
	
	$("body").append("<div id='div_data_hidden' style='background-image: url(" + url +  ");'></div>");	
	
}, 3000);
