---
layout: post
title: "Grid Plane"
date: 2018-01-04
categories:
  - Threejs
description: Grid plane   
image: /../assets/threejs/screenshot/gridPlane.png
image-sm: /../assets/threejs/screenshot/gridPlane.png
---

<script src="https://code.jquery.com/jquery-1.9.1.min.js"></script>
<script type="text/javascript" src="{{ site.url }}/assets/threejs/build/three.js"></script>
<script type="text/javascript" src="{{ site.url }}/assets/threejs/js/Detector.js"></script>
<script type="text/javascript" src="{{ site.url }}/assets/threejs/js/libs/stats.min.js"></script>
<script src="{{ site.url }}/assets/threejs/js/controls/TransformControls.js"></script>
<script src="{{ site.url }}/assets/threejs/js/controls/OrbitControls.js"></script>
<script src="{{ site.url }}/assets/threejs/js/libs/dat.gui.min.js"></script>
<div id="threejsView"></div>
<script type="text/javascript">
	if(!Detector.webgl){
		Detector.addGetWebGLMessage();
	}
	var container, camera, scene, renderer, boxMesh;
	var transformControl; 	//트랜스폼 컨트롤러 
	var stats; 
	var params = {
			xRotate : false,
			yRotate : false,
			zRotate : false
	}
	function onWindowResize(){
		camera.aspect = window.innerWidth / window.innerHeight;
		camera.updateProjectionMatrix();
		renderer.setSize(window.innerWidth, window.innerHeight);
	}
	//초기화 함수 
	function init(){
		container = document.createElement('div');
		container.style.width = '100%';
		container.style.minHeight = '500px';		
		container.style.height = '100%';
		$('#threejsView').append(container);
		// stats 
		stats = new Stats(); 								//stats 객채 생성 
		container.appendChild(stats.dom);		//container에 stats dom append
		//카메라 
		camera = new THREE.PerspectiveCamera(45, window.innerWidth / window.innerHeight, 1, 10000);
		camera.position.set(500,800,1300);
		camera.lookAt(new THREE.Vector3());
		//씬
		scene = new THREE.Scene();
		scene.background = new THREE.Color(0xf0f0f0);
		//그리드 
		var gridHelper = new THREE.GridHelper(1000, 20);
		scene.add(gridHelper);	
		//지오메트리 
		var geometry = new THREE.PlaneBufferGeometry(1000, 1000);
		geometry.rotateX(-Math.PI/2);
		//박스 생성
		var boxTexture = new THREE.TextureLoader().load('{{ site.url }}/assets/threejs/textures/crate.gif');		//박스 텍스쳐 가져오기 
		var boxGeometry = new THREE.BoxBufferGeometry(200, 200, 200);																						//박스 지오메트리
		var boxMaterial  = new THREE.MeshBasicMaterial({map:boxTexture});																				//박스 메터리얼
		boxMesh = new THREE.Mesh(boxGeometry, boxMaterial);
		scene.add(boxMesh);
		//바닥 메시 생성 
		plane = new THREE.Mesh(geometry, new THREE.MeshBasicMaterial({visible:false}));
		scene.add(plane);
		//directional Light 조명 
		var directionalLight = new THREE.DirectionalLight(0xffffff);
		directionalLight.position.set(1,0.75,0.5).normalize();
		scene.add(directionalLight);
		//랜더러
		renderer = new THREE.WebGLRenderer({antialias:true});
		renderer.setPixelRatio(window.devicePixelRatio);
		renderer.setSize($('.post').innerWidth(), $('.post').innerWidth() * 2);
		container.appendChild(renderer.domElement);
		//TransformControls 생성
		transformControl = new THREE.TransformControls(camera, renderer.domElement);
		transformControl.addEventListener('change', render);
		scene.add(transformControl);
		//OrbitControls 생성 - 마우스 조작 컨트롤러
		var controls = new THREE.OrbitControls(camera, renderer.domElement);
		controls.damping = 0.2;
		transformControl.attach(boxMesh);
		//GUI 생성 
		var gui = new dat.GUI();
		gui.add(params, 'xRotate');
		gui.add(params, 'yRotate');
		gui.add(params, 'zRotate');
		gui.open();
		//윈도우 리사이즈 이벤트 리스너 등록
		window.addEventListener('resize', onWindowResize, false);
	}
	// 그리기 함수 
	function render(){
		renderer.render(scene,camera);
	}
	function animate(){
		requestAnimationFrame(animate);
		if(params.xRotate){
			boxMesh.rotation.x += 0.01;	
		}
		if(params.yRotate){
			boxMesh.rotation.y += 0.01;	
		}
		if(params.zRotate){
			boxMesh.rotation.z += 0.01;	
		}
		renderer.render(scene,camera);
		stats.update();
		transformControl.update();
	}
	init();
	animate();
</script>



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