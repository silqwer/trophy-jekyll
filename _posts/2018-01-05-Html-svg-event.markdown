---
layout: post
title: "Html svg evnet test"
date: 2018-01-05
categories:
  - Test
description: Html으로 불러온 svg에서 svg관련 event가 동작하는지 테스트  
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
	$( window ).on( "load", function() {
		var object  = document.getElementById("svgObj");
		console.log(object);
		var svgDoc = object.contentDocument;
		var background = svgDoc.getElementById("background");
		console.log(background);
		
		background.setAttribute("fill", "yellow");
		
		background.addEventListener("click", function(){
			console.log('mouse move');
			$('body').append('<p>마우스 클릭</p>');
			alert('클릭');
		});
		
		background.addEventListener("mousemove", function(){
			console.log('mouse move');
			$('body').append('<p>마우스 움직임</p>');
			alert('움직임');
		});
		
		background.addEventListener("SVGScroll", function(){
			console.log('SVGScroll');
			$('body').append('<p>마우스 스크롤</p>');
			alert('스크롤');
		});
		
	});
	
	function colorChange(btnsObj, btnObj){
		btnsObj.css('background-color', 'gray');
		btnObj.css('background-color', 'red');
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

<object id="svgObj" width="100%" height="600"  type="image/svg+xml" data="{{ site.url }}/assets/resources/file/ARS2018299914467.svg" ></object>

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
	
