---
layout: post
title: "Basic Arjs"
date: 2018-07-15
categories:
  - ARjs
description: Ar.js 돌려보기    
image: /../assets/threejs/screenshot/gridPlane.png
image-sm: /../assets/threejs/screenshot/gridPlane.png
---
<script src="{{ site.url }}/assets/arjs/vendor/aframe.min.js"/>
<script src="{{ site.url }}/assets/arjs/build/aframe-ar.js"/>
<div style="margin:0px; overflow:hidden;">
	<a-scene embedded arjs>
  		<a-marker preset="hiro">
          <a-box position='0 0.5 0' material='color: black;'></a-box>
  		</a-marker>
  		<a-entity camera></a-entity>
    </a-scene>
</div>
