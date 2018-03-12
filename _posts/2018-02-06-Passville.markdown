---
layout: post
title: "Passville"
date: 2018-02-06
categories:
  - Portfolio
description: 하이브리드 웹 앱 문제풀이, 패스빌 
image: /../assets/img/pass/img4.png
image-sm: /../assets/img/pass/img4.png
---

<div class="container">
	<div id="slides">
		<img src="{{ site.url }}/assets/img/pass/img.png" alt="1">
		<img src="{{ site.url }}/assets/img/pass/img2.png" alt="2">
		<img src="{{ site.url }}/assets/img/pass/img3.png" alt="3">
		<img src="{{ site.url }}/assets/img/pass/img4.png" alt="4">
		<img src="{{ site.url }}/assets/img/pass/img5.png" alt="5">
		<img src="{{ site.url }}/assets/img/pass/img6.png" alt="6">
		<img src="{{ site.url }}/assets/img/pass/img7.png" alt="7">
		<img src="{{ site.url }}/assets/img/pass/img8.png" alt="8">
		<img src="{{ site.url }}/assets/img/pass/img9.png" alt="9">
		<img src="{{ site.url }}/assets/img/pass/img10.png" alt="10">
		<img src="{{ site.url }}/assets/img/pass/img11.png" alt="11">
		<img src="{{ site.url }}/assets/img/pass/img12.png" alt="12">
		<img src="{{ site.url }}/assets/img/pass/img13.png" alt="13">
		<img src="{{ site.url }}/assets/img/pass/img14.png" alt="14">
		<img src="{{ site.url }}/assets/img/pass/img15.png" alt="15">
		<img src="{{ site.url }}/assets/img/pass/img16.png" alt="16">
		<img src="{{ site.url }}/assets/img/pass/img17.png" alt="17">
		<img src="{{ site.url }}/assets/img/pass/img18.png" alt="18">
	</div>
</div>

<script src="https://code.jquery.com/jquery-1.9.1.min.js"></script>
<script src="{{ site.url }}/assets/slider/js/jquery.slides.min.js"></script>
<script>
	$(function() {
		$('#slides').slidesjs({
        width: 940,
        height: 528,
        play: {
        		active: true,
          		auto: true,
          		interval: 1000,
          		swap: true
        	}
      	});
    });
</script>

자격증 문제풀이 앱 패스빌 

<h3>구현기능</h3>
<ol>
  <li>문제풀이</li>
  <li>모의고사</li>
  <li>오답노트</li>
  <li>문자발송 연동</li>
</ol>

<figure>
	<iframe width="388" height="585" src="https://www.youtube.com/embed/x79gUNFlBBE" frameborder="0" allowfullscreen></iframe>
 	<figcaption>패스빌(Passville) 구동</figcaption>   
</figure>

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
