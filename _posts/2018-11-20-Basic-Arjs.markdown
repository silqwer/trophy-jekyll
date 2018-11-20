---
layout: post
title: "Basic Arjs"
date: 2018-11-20
categories:
  - ARjs
description: Ar.js 돌려보기    
image: /../assets/threejs/screenshot/gridPlane.png
image-sm: /../assets/threejs/screenshot/gridPlane.png
---
<script src="{{ site.url }}/assets/resources/lib/arjs/aframe.min.js"/>
<script src="{{ site.url }}/assets/resources/lib/arjs/aframe-ar.js"/>
<div style="margin:0px; overflow:hidden;">
	<a-scene embedded arjs>
  		<a-marker preset="hiro">
          <a-box position='0 0.5 0' material='color: black;'></a-box>
  		</a-marker>
  		<a-entity camera></a-entity>
    </a-scene>
</div>
