---
layout: post
title: "Mouse wheel event test"
date: 2018-01-06
categories:
  - Test
description: 마우스 휠 이벤트 입력 테스트 
image: /../assets/resources/img/test/background.png
image-sm: /../assets/resources/img/test/background.png
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
	width: 100%;
    height: 500px;
    background-color: antiquewhite;
}

.btn{
	width: 50%;
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

<h1 id="result">스크롤을 해주세요.</h1>

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
