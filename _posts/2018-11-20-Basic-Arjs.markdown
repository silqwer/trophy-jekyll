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

# Ar.js 기본 예제
```html
<body style='margin : 0px; overflow: hidden;'>
<a-scene embedded arjs>
	<a-marker preset="hiro">
    	<a-box position='0 0.5 0' material='color: black;'></a-box>
	</a-marker>
	<a-entity camera>
	</a-entity>
</a-scene>
```

<iframe width="100%" height="500px;" src="{{ site.url }}/assets/resources/html/basicAr.html"></iframe>