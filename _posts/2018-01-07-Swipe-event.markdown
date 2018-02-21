---
layout: post
title: "Swipe event test"
date: 2018-01-07
categories:
  - Test
description: Jquery mobile swipe 이벤트 테스트  
image: /../assets/img/pass/img4.png
image-sm: /../assets/img/pass/img4.png
---

<script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
<script src="https://code.jquery.com/mobile/1.5.0-alpha.1/jquery.mobile-1.5.0-alpha.1.min.js"></script>
<script>
var arr = [
	'btn1',
	'btn2',
	'btn3'
];
var arrIdx = 0; 
	
$(document).ready(function(){
	$( "#background" ).on( "swipeleft", function(){
		console.log('왼쪽 감소');
			if(arrIdx > 0)
				--arrIdx; 
		colorChange(arr[arrIdx]);
	});
			
	$( "#background" ).on( "swiperight", function(){
		console.log('오른쪽 증가');
		if(arr.length-1 > arrIdx)
			++arrIdx; 
		colorChange(arr[arrIdx]);	
	});
});
		
	function colorChange(id){
		$('.btn').css('background-color', 'gray');
		$('#'+id).css('background-color', 'red');
	}
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
		position: relative;
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

<h1 id="result">스와이프 해주세요.</h1>
