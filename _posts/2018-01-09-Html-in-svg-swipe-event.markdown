---
layout: post
title: "Html in svg swipe evnet test"
date: 2018-01-08
categories:
  - Test
description: SVG 함수 touchstart와 touchend를 이용해 만든 swpie 함수와 colorChange 함수 테스트
image: /../assets/img/test/background.png
image-sm: /../assets/img/test/background.png
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
	
	var touchStartPoint = {
		x : 0, 
		y : 0
	};
	
	var touchEndPoint = {
		x : 0, 
		y : 0
	};
	
	var swipe = function(s,e){
		
		console.log('start point:('+s.x+', '+s.y+')');
		console.log('ende point:('+e.x+', '+e.y+')');
		
		var avsX = Math.abs(s.x - e.x);
		var avsY = Math.abs(s.y - e.y);
		
		if(avsX > avsY){
			//x 방향으로 스와이프
			if(s.x > e.x){
				//엔드가 크면 오른쪽 , 작으면 왼쪽 
				console.log('LEFT');
				if(arrIdx > 0)
					--arrIdx;
			}else{
				console.log('RIGHT');
				if(arr.length-1 > arrIdx)
					++arrIdx;
			}
		}else{
			//y 방향으로 스와이프
			if(s.y > e.y){
				//엔드가 크면 아래 , 작으면 왼쪽 
				console.log('UP');
			}else{
				console.log('DOWN');
			}
		}
	};
	
	$( window ).on( "load", function() {
		var object  = document.getElementById("svgObj");
		var svgDoc = object.contentDocument;
		var background = svgDoc.getElementById("background");
		console.log(background);
		// 터치 스타트 
		background.addEventListener("touchstart", function(e){
			console.log('touchstart');
			console.log(e);
			touchStartPoint.x = e.changedTouches[0].clientX; 
			touchStartPoint.y = e.changedTouches[0].clientY; 
			
			console.log('touchStartPoint:'+touchStartPoint);
	
		});
		
		// 터치 엔드 
		background.addEventListener("touchend", function(e){
			console.log('touchend');
			console.log(e);
			
			touchEndPoint.x = e.changedTouches[0].clientX; 
			touchEndPoint.y = e.changedTouches[0].clientY; 
			
			console.log('touchEndPoint:'+touchEndPoint);
			
			swipe(touchStartPoint, touchEndPoint);
			
			var btns = svgDoc.getElementsByClassName("btn");
			var btnName = arr[arrIdx];
			var btn = svgDoc.getElementById(btnName);
			
			colorChange(btns, btn);
		});
		
	});
	
	function colorChange(btnsObj, btnObj){
		for(let btn of btnsObj){
			btn.style.fill = "gray";
		}

		btnObj.style.fill = "red";
	}
	
</script>

<object id="svgObj" width="100%" height="600"  type="image/svg+xml" data="{{ site.url }}/assets/file/ARS2018299914467.svg" ></object>
<h1 id="result">스와이프를 해주세요.</h1>
