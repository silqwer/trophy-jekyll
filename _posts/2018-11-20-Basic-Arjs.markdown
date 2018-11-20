---
layout: post
title: "Arjs Basic"
date: 2018-11-20
categories:
  - ARjs
description: Ar.js 돌려보기    
image: /../assets/threejs/screenshot/gridPlane.png
image-sm: /../assets/threejs/screenshot/gridPlane.png
---
<script>
	var min = document.createElement('script');
	min.src = '{{ site.url }}/assets/resources/lib/arjs/aframe.min.js';
	document.head.appendChild(min);
	var ar = document.createElement('script');
	ar.src = '{{ site.url }}/assets/resources/lib/arjs/aframe-ar.js';
	document.head.appendChild(ar);
</script>
<div style="margin:0px; overflow:hidden;">
	<a-scene embedded arjs>
  		<a-marker preset="hiro">
          <a-box position='0 0.5 0' material='color: black;'></a-box>
  		</a-marker>
  		<a-entity camera></a-entity>
    </a-scene>
</div>
