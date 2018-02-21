---
layout: post
title: "Mouse wheel event test"
date: 2018-01-06
categories:
  - Test
description: 마우스 휠 이벤트 테스트  
image: /../assets/img/pass/img4.png
image-sm: /../assets/img/pass/img4.png
---

<script>
var lastScrollTop = 0; 
document.addEventListener("DOMContentLoaded", function(){
	// Handler when the DOM is fully loaded
	var arr = [
		'btn1',
		'btn2',
		'btn3'
	];
	
	var arrIdx = 0; 
	document.getElementById("background").addEventListener("wheel", function(e){
		
		
		if (e.deltaY < 0) {
			console.log('scrolling up');
			console.log('감소 전:'+arrIdx);
			if(arrIdx > 0)
				--arrIdx; 
		}
		  
		if (e.deltaY > 0) {
			console.log('scrolling down');
			console.log('증가 전:'+arrIdx);
			if(arr.length-1 > arrIdx)
				++arrIdx; 
		}
		
		var btns = document.getElementsByClassName('btn');
		for (let btn of btns) { 
			btn.style.backgroundColor = "gray";
		}
	
		document.getElementById(arr[arrIdx]).style.backgroundColor = "red";
		console.log('결과:'+arr[arrIdx]);
	});
});
</script>
<style>
#background{
	width: 500px;
    height: 500px;
    background-color: antiquewhite;
}

.btn{
	width: 250px;
    height: 50px;
    background-color: gray;
    position: absolute;
    top: 360px;
    left: 135px;
}

#btn1{
    top: 100px;
}

#btn2{
    top: 200px;
}

#btn3{
    top: 300px;
}
</style>

<div id="background">
	<div id="btn1" class="btn"></div>
	<div id="btn2" class="btn"></div>
	<div id="btn3" class="btn"></div>
</div>

<h1 id="result">스크롤을 해주세요.</h1>
