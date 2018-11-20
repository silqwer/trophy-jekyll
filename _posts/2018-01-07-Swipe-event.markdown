---
layout: post
title: "Swipe event test"
date: 2018-01-07
categories:
  - Test
description: SVG file에 jquery.mobile을 넣고 swipe 함수가 동작하는지 확인하는 테스트
image: /../assets/resources/img/test/background.png
image-sm: /../assets/resources/img/test/background.png
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
		width: 100%;
		height: 500px;
		background-color: antiquewhite;
	}

	.btn{
		width: 50%;
		height: 50px;
		background-color: gray;
		position: relative;
		left: 120px;
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

<div id="disqus_thread"></div>
<script>

/**
*  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
*  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables*/
/*
var disqus_config = function () {
this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};
*/
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = 'https://silqwer.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>