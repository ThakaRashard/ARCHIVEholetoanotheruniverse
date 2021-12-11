<style>

.firstcharacter {
    color: #fff;
  text-shadow:
      0 0 7px #fff,
      0 0 10px #fff,
      0 0 21px #fff,
      0 0 42px #0fa,
      0 0 82px #0fa,
      0 0 92px #0fa,
      0 0 102px #0fa,
      0 0 151px #0fa;
  float: left;
  font-size: 75px;
  line-height: 60px;
  padding-top: 4px;
  padding-right: 8px;
  padding-left: 3px;
}

.neonText {
  color: #fff;
  text-shadow:
      0 0 7px #fff,
      0 0 10px #fff,
      0 0 21px #fff,
      0 0 42px #0fa,
      0 0 82px #0fa,
      0 0 92px #0fa,
      0 0 102px #0fa,
  
}	
	
li a:hover {
 color: #c9ff23;

     
}	

	
.glow {
  color: #fff;
  text-align: center;
  animation: glow 3s ease-in-out infinite alternate;
}

@-webkit-keyframes glow {
  from {
    text-shadow: 0 0 10px #fff, 0 0 20px #fff, 0 0 30px #008000, 0 0 40px #008000, 0 0 50px #008000, 0 0 60px #008000, 0 0 70px #e60073;
  }
  
  to {
    text-shadow: 0 0 20px #fff, 0 0 30px #ff4da6, 0 0 40px #ff4da6, 0 0 50px #ff4da6, 0 0 60px #ff4da6, 0 0 70px #ff4da6, 0 0 80px #ff4da6;
  }
}
	
	
	
.some-page-wrapper {
  margin: 15px;
  background-color: ##23b2ff;
}

.row {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  width: 100%;
}

.column {
  display: flex;
  flex-direction: column;
  flex-basis: 100%;
  flex: 1;
  overflow: hidden;
}

.double-column {
  display: flex;
  flex-direction: column;
  flex-basis: 100%;
  flex: 2;
  overflow: hidden;
}

.blue-column {
  background-color: #23ff32;
  
}

.green-column {
    
    background-color: #c9ff23;
}	
	
	
	
	
	
	
</style>

<span class="glow">  # #!/usr/bin/ruby -w --debug  </span>

## ONE_DAY_MY_BLOG_WiLL_RETURN TRUE when run from the command line 


Hole To Another Universe  
<ul>
  <li><a href="#home">1 # HOLE_TO_ANOTHER_UNiVERSE###BLOG##################</a></li>
  <li><a href="#news">2 # TO###MY_RESUME###################################</a></li>
  <li><a href="#contact">3 # ANOTHER###SANDBOX################################</a></li>
  <li><a href="#about">4 # UNiVERSALCONTACKT################################</a></li>
</ul>
<script language="javascript">
alert("Hello there, and welcome.")
</script>
##START#######MMAKING_PLANS_##4_SAATU####TUPAC_PLEASE_GUIDE_ME
# LATEST_POST ############# ~>
<div class="codepen" data-height="300" data-theme-id="dark" data-default-tab="css,result" data-slug-hash="pgPgeb" data-editable="true" data-user="Yakudoo"  data-prefill='{"title":"Low Poly Tree Generator","description":"This is an attempt to generate a tree that grows, and progressively creates its own leaves, foliage, fruits etc... Some trees are more elegant than others :) It was initially made for this project : http://www.meusinvest.be/2016/","tags":["webgl","threejs","low-poly","tree","generator"],"scripts":["https://s3-us-west-2.amazonaws.com/s.cdpn.io/264161/Math2.js","https://cdnjs.cloudflare.com/ajax/libs/stats.js/r14/Stats.min.js","https://cdnjs.cloudflare.com/ajax/libs/three.js/r73/three.min.js","https://s3-us-west-2.amazonaws.com/s.cdpn.io/264161/GeometryHelpers.js","https://cdnjs.cloudflare.com/ajax/libs/gsap/1.16.1/TweenMax.min.js","https://s3-us-west-2.amazonaws.com/s.cdpn.io/264161/scene_colors.js","https://s3-us-west-2.amazonaws.com/s.cdpn.io/264161/OrbitControls.js","https://s3-us-west-2.amazonaws.com/s.cdpn.io/264161/CustomMeshFlat.js","https://s3-us-west-2.amazonaws.com/s.cdpn.io/264161/dat.gui.min.js"],"stylesheets":[]}'>
  <pre data-lang="html">	&lt;div id="world"/>

&lt;div id="credits">
  - Press and drag to turn around -
  &lt;p>&lt;a href="https://codepen.io/Yakudoo/"  target="blank">my other codepens&lt;/a>  | &lt;a href="https://www.epic.net" target="blank">epic.net&lt;/a> | &lt;a href="http://www.meusinvest.be/2016/" target="blank">Created initially for this project&lt;/a>&lt;/p>
&lt;/div></pre>
  <pre data-lang="css">@import url(https://fonts.googleapis.com/css?family=Open+Sans:800);

#world{
	position: absolute;
	width:100%;
	height: 100%;
	background: #cefaeb;
  overflow:hidden;
}

#credits{
  position:absolute;
  width:100%;
  margin: auto;
  bottom:0;
  margin-bottom:20px;
  font-family:'Open Sans', sans-serif;
  color:#f7e1be;;
  font-size:0.7em;
  text-transform: uppercase;
  text-align : center;
  line-height:1.5;
  letter-spacing: 2px;
}

#credits a {
  color:#dbf4e8;
}

#credits a:hover {
  color:#fb5d24;
}</pre>
  <pre data-lang="js">/*
Used initially for a client to create this greeting card :
http://www.meusinvest.be/2016/
*/

////////////////////////////////////////////////
//                  THREE JS RELATED VARIABLES
////////////////////////////////////////////////

var scene,
    camera, fieldOfView, aspectRatio, nearPlane, farPlane,
    renderer,
    container,
    controls,
    mouseDown = false;
////////////////////////////////////////////////
//                      SCREEN & MOUSE VARIABLES
////////////////////////////////////////////////

var HEIGHT, WIDTH, windowHalfX, windowHalfY,
    mousePos = { x: 0, y: 0 },
    oldMousePos = {x:0, y:0};

////////////////////////////////////////////////
//                           3D MODELS VARIABLES
////////////////////////////////////////////////
var floor, tree,
    globalWind = 0,
    trees = [],
    waitingParticles = [],
    flyingParticles = [],
    foliages = [],
    foliagesComplex = [];

////////////////////////////////////////////////
//                                   STATS & GUI
////////////////////////////////////////////////
var stats;
var parameters = {
  truncHeight:100,
  truncThickness:4,
  truncColor:Colors.grey_d,
  truncNoise:.5,
  foliageColor:"pinks",
  foliageDensity:5,
  foliageNoise:.05,
  foliageSize : 10,
  animationSpeed: 2.5,
};

function initGUI(){
  var gui = new dat.GUI();
  gui.width = 250;
  gui.add(parameters, 'truncHeight').min(60).max(110).step(10).name('Trunc Height');
  gui.add(parameters, 'truncThickness').min(2).max(6).step(1).name('Trunc Thickness');
  gui.add(parameters, 'truncNoise').min(0).max(5).step(.5).name('Trunc Disp.');
  gui.add(parameters, 'truncColor', {
    "Light White":Colors.white_l,
    "Dark White":Colors.white_d,
    "Light Grey":Colors.grey_l,
    "Dark Grey":Colors.grey_d
  }).name('Trunc Color');
  gui.add(parameters, 'foliageColor', {
    "White":"whites",
    "Grey":"greys",
    "Pink":"pinks",
    "Yellow":"yellows",
    "Purple":"purples"
  }).name('Foliage Color');
  gui.add(parameters, 'foliageDensity').min(3).max(8).step(1).name('Foliage Density');
  gui.add(parameters, 'foliageNoise').min(0).max(.2).step(.01).name('Foliage Disp.');
  gui.add(parameters, 'foliageSize').min(5).max(30).step(1).name('Foliage Size.');
  //gui.add(parameters, 'animationSpeed').min(1).max(4).step(.5).name('Anim. Speed');
  
  
  gui.add({generate:function(){createTree()}}, 'generate').name(">GENERATE");
}

////////////////////////////////////////////////
//                  INIT THREE JS, MOUSE, SCREEN
////////////////////////////////////////////////

function initCore() {
  
  HEIGHT = window.innerHeight;
  WIDTH = window.innerWidth;
  windowHalfX = WIDTH / 2;
  windowHalfY = HEIGHT / 2;

  scene = new THREE.Scene();
  var fogcol = 0xcefaeb;//0x1c0403
  scene.fog = new THREE.FogExp2( fogcol, 0.0028 ); //new THREE.Fog(fogcol, 300, 1000);
  aspectRatio = WIDTH / HEIGHT;
  fieldOfView = 60;
  nearPlane = .1;
  farPlane = 3000;
  camera = new THREE.PerspectiveCamera(
    fieldOfView,
    aspectRatio,
    nearPlane,
    farPlane
    );
  camera.position.x = 0;
  camera.position.z = 150;
  camera.position.y = 100;
  
  renderer = new THREE.WebGLRenderer({ alpha: true, antialias: true });
  renderer.setSize(WIDTH, HEIGHT);
  renderer.shadowMap.enabled = true;
  
  container = document.getElementById('world');
  container.appendChild(renderer.domElement);
  
  window.addEventListener('resize', handleWindowResize, false);
  document.addEventListener('mousemove', handleMouseMove, false);
  document.addEventListener('touchmove', handleTouchMove, false);
  document.addEventListener('touchmove', handleTouchMove, false);
  document.addEventListener('mousedown', mouseDownHandler, false);
  document.addEventListener('mouseup', mouseUpHandler, false);
  
  //*
  controls = new THREE.OrbitControls(camera, renderer.domElement);
  controls.target = new THREE.Vector3(0,60,0);
  controls.minPolarAngle = -Math.PI*.45; 
  controls.maxPolarAngle = Math.PI*.45;
  controls.minDistance = 130;
  controls.maxDistance = 500;
  //controls.enabled = false;
  //controls.noZoom = true;
  //controls.noPan = true;
  //*/

  console.log(controls);
}

////////////////////////////////////////////////
//                  MOUSE EVENTS / SCREEN EVENTS
////////////////////////////////////////////////

function handleWindowResize() {
  HEIGHT = window.innerHeight;
  WIDTH = window.innerWidth;
  windowHalfX = WIDTH / 2;
  windowHalfY = HEIGHT / 2;
  renderer.setSize(WIDTH, HEIGHT);
  camera.aspect = WIDTH / HEIGHT;
  camera.updateProjectionMatrix();
}

function mouseDownHandler(event) {
  mouseDown = true;
} 
function mouseUpHandler(event) {
  mouseDown = false;
} 

function handleMouseMove(event) {
  mousePos = {x:event.clientX, y:event.clientY};
} 

function handleTouchMove(event) {
  if (event.touches.length == 1) {
    event.preventDefault();
    mousePos = {x:event.touches[0].pageX, y:event.touches[0].pageY};
  }
}
////////////////////////////////////////////////
//                                        RENDER
////////////////////////////////////////////////

function render(){
  if (controls && controls.enabled) controls.update();
  renderer.render(scene, camera);
}

////////////////////////////////////////////////
//                                        LIGHTS
////////////////////////////////////////////////
var gobalLight, shadowLight, backLight;

function createLights() {

  var globalLight = new THREE.HemisphereLight(Colors.white_d, Colors.white_d, .8)
  /*
  var pointLight = new THREE.PointLight( Colors.pink_l, 1, 300 );
  pointLight.position.set( 35, 50, 30 );
  var sphereSize = 10;
  var pointLightHelper = new THREE.PointLightHelper( pointLight, sphereSize );
  //*/
  shadowLight = new THREE.DirectionalLight(0xffffff, 1);
  shadowLight.position.set(100, 150, 100);
  shadowLight.castShadow = true;
  shadowLight.shadowDarkness = .2;
  shadowLight.shadowMapWidth = shadowLight.shadowMapHeight = 1024;
  scene.add(shadowLight);
  //scene.add(pointLight );  
  scene.add(globalLight);  
}
////////////////////////////////////////////////
//                                        FLOOR
////////////////////////////////////////////////
var Floor = function(){
  var floorCol = Colors.green_d;
  this.mesh =  new CustomMesh.PlaneMesh(1600,1600,12, floorCol);
  var vertices = this.mesh.geometry.vertices;
  for (var i=0; i&lt;vertices.length; i++){
    var v = vertices[i];
    v.x += Math2.rangeRandom(-10,10);
    v.y += Math2.rangeRandom(-10,10);
    v.z += Math2.rangeRandom(-10,10);
  }
  this.mesh.geometry.computeFaceNormals();
  this.mesh.geometry.verticesNeedUpdate = true;
  this.mesh.geometry.colorsNeedUpdate = true;
  //
  //this.mesh.geometry.computeVertexNormals();
  this.mesh.rotation.x = -Math.PI / 2;
}


////////////////////////////////////////////////
//                                 CREATE MODELS
////////////////////////////////////////////////

// FLOOR

function createFloor(){ 
  floor = new Floor();
  scene.add(floor.mesh);
}

// FOREST

function createForest(){
  var nTrees = 25;
  var treesDist = 25;
  for (var i = 0; i&lt; nTrees; i++){
    var tree = new Tree(false);
    tree.mesh.position.y = -5;
    tree.mesh.position.x = -((nTrees/2)*treesDist) + (i*treesDist);
    tree.mesh.position.z = -Math.random()*150 -150;
    scene.add(tree.mesh);
    trees.push(tree);
  } 
}

// TREE

function createTree(){
  if (tree){
    tree.fly(function(){
      scene.remove(tree.mesh);
      tree.kill();
      tree = null;
      foliagesComplex = [];
      createTree();
    })
  }else{
    tree = new Tree(true);
    tree.mesh.position.y = -10;
    scene.add(tree.mesh);
    tree.trunc.grow();
    updateShadows();  
  } 
}


////////////////////////////////////////////////
//                                        MODELS
////////////////////////////////////////////////

// TREE

Tree = function(complex){
	this.mesh = new THREE.Object3D();
	this.trunc = new Trunc(complex);
	this.mesh.add(this.trunc.mesh);
}

Tree.prototype.kill = function(){
  this.trunc.kill();
  this.mesh = null;
}

Tree.prototype.fly = function(callback){
  TweenMax.to(this.mesh.position, 1.5, {x:100, y:300, z:300, ease:Strong.easeIn, onComplete:function(){
    if (callback) callback();
  }});
  
  TweenMax.to(this.mesh.rotation, 2, {z:-Math.PI/6, y:Math.PI/2, ease:Strong.easeInOut});
  TweenMax.to(this.mesh.scale, 1.5, {y:1.1, x:.9, ease:Strong.easeInOut});
}

// TRUNC

Trunc = function(complex){
  this.type = "trunc";
	this.pointsTrunc = [];
	this.hierarchy = 1;
  
	// parametrables
	this.truncColor = (complex) ? parameters.truncColor : Colors.getRandomFrom(Colors.trunc);
	this.truncHeight = (complex) ? parameters.truncHeight : Math2.rangeRandom(70,100);
	this.truncStartRadius = (complex) ? parameters.truncThickness : Math2.rangeRandom(2,4); 
	this.verticalSegments = (complex)? Math2.rangeRandomInt(9,12) : Math2.rangeRandomInt(3,5);
	this.radiusSegments = (complex)? Math2.rangeRandomInt(6,10) : Math2.rangeRandomInt(4,6);
	this.shapeAngleStart = Math2.rangeRandom(Math.PI/4, Math.PI/2); 
	this.shapeAmplitude = Math2.rangeRandom(this.truncStartRadius/4, this.truncStartRadius*6);
	this.noise = (complex)? parameters.truncNoise : Math2.rangeRandom(this.truncStartRadius/8, this.truncStartRadius/4);
  this.foliageDensity = (complex)? parameters.foliageDensity : 2;
	this.shapeAngle = Math.PI - this.shapeAngleStart;
	this.freq = this.shapeAngle/this.verticalSegments;
	this.segHeight = (this.truncHeight / this.verticalSegments);
	
  /*
	console.log("this.truncColor",this.truncColor);
	console.log("this.truncHeight",this.truncHeight);
	console.log("this.truncStartRay",this.truncStartRay);
	console.log("this.verticalSegments",this.verticalSegments);
	console.log("this.shapeAngleStart",this.shapeAngleStart);
	console.log("this.shapeAmplitude",this.shapeAmplitude);
	console.log("this.noise",this.noise);
	console.log("this.shapeAngle",this.shapeAngle);
	console.log("this.freq",this.freq);
	console.log("this.segHeight",this.segHeight);
	*/

	this.pointsTrunc.push( new THREE.Vector3( 0, 0, 0 ) );  
  var ty,tx, tz, i;
  ty = 0;
	for ( i = 0; i &lt; this.verticalSegments; i ++ ) {
		tx = Math.sin( this.shapeAngleStart + (i * this.freq) ) * this.shapeAmplitude + this.truncStartRadius;
		tz = 0;
		this.pointsTrunc.push( new THREE.Vector3( tx, ty, tz ) );
		if (i &lt; this.verticalSegments -1) {
		  ty += this.segHeight;
		}else{
		  ty += this.segHeight/4;
		}
	}
	this.pointsTrunc.push( new THREE.Vector3( 0, ty, 0 ) );
	this.mesh = new CustomMesh.Lathe( this.pointsTrunc, this.radiusSegments, this.truncColor);
	this.mesh.userData.hierarchy = this.hierarchy;
  this.mesh.userData.refClass = this;
	var geom = this.mesh.geometry;
	
	var defAttachs;
  if (complex){
    defAttachs = [
			{
       type:"elbowBranch", 	
       count : this.foliageDensity, 	
       minH : this.truncHeight*.75, 	
       maxH:this.truncHeight*.95, 	
       minAngle:0,//-Math.PI*3/4, 			
       maxAngle:0,//-Math.PI/4 	
      },
      /*
			{
        type:"elbowBranch",	
        count : 1, 	
        minH : this.truncHeight*.75, 	
        maxH:this.truncHeight*.95, 	
        minAngle:Math.PI/4, 			
        maxAngle:Math.PI*3/4	
      },
      
      {
        type:"elbowBranch",	
        count : 1, 	
        minH : this.truncHeight*.8, 	
        maxH:this.truncHeight*1, 	
        minAngle:-Math.PI/4, 			
        maxAngle:Math.PI/4	
      },
			*/
			{
        type:"branch", 	
        count : 1, 	
        minH : this.truncHeight*.45, 	
        maxH:this.truncHeight*.75, 	
        minAngle:-Math.PI, 				
        maxAngle:0 	
      },
			{
        type:"branch", 	
        count : 1, 	
        minH : this.truncHeight*.35, 	
        maxH:this.truncHeight*.50, 	
        minAngle:Math.PI/4, 			
        maxAngle:Math.PI*3/4    
      },
			{
        type:"leaf", 		
        count : 5, 	
        minH : this.truncHeight*.30, 	
        maxH:this.truncHeight*.90, 	
        minAngle:0, 		
        maxAngle:0	
      },
			{
        type:"fruit",		
        count : 4, 	
        minH : this.truncHeight*.30, 	
        maxH:this.truncHeight*.80, 	
        minAngle:0, 		
        maxAngle:0	
      },
			{
        type:"spike", 		
        count : 6, 	
        minH : this.truncHeight*.10, 	
        maxH:this.truncHeight*.90, 	
        minAngle:0, 		
        maxAngle:0	
      },
			{
        type:"moss", 		
        count : 6, 	
        minH : this.truncHeight*.10, 	
        maxH:this.truncHeight*.90, 	
        minAngle:0, 		
        maxAngle:0	
      },	
		];
  }else{
    defAttachs = [
			{
       type:"elbowBranch", 	
       count : 1, 	
       minH : this.truncHeight*.75, 	
       maxH:this.truncHeight*.9, 	
       minAngle:-Math.PI*3/4, 			
       maxAngle:-Math.PI/4 	
      },
      
			{
        type:"elbowBranch",	
        count : 1, 	
        minH : this.truncHeight*.45, 	
        maxH:this.truncHeight*.7, 	
        minAngle:Math.PI/4, 			
        maxAngle:Math.PI*3/4	
      },
			
			{
        type:"branch", 	
        count : 1, 	
        minH : this.truncHeight*.45, 	
        maxH:this.truncHeight*.75, 	
        minAngle:-Math.PI, 				
        maxAngle:0 	
      },
			{
        type:"branch", 	
        count : 1, 	
        minH : this.truncHeight*.15, 	
        maxH:this.truncHeight*.45, 	
        minAngle:Math.PI/4, 			
        maxAngle:Math.PI*3/4    
      },
			
			{
        type:"fruit",		
        count : 2, 	
        minH : this.truncHeight*.30, 	
        maxH:this.truncHeight*.80, 	
        minAngle:0, 		
        maxAngle:0	
      },
		];
  }
	
	this.attachsVerts = GeometryHelpers.getAttachs(geom, defAttachs);	
	if (this.noise) GeometryHelpers.makeNoise(geom, this.noise);
	this.verticesNormals = GeometryHelpers.getVerticesNormals(geom);
  
  CustomMesh.flatshadeGeometry(geom);

	var cols = [];
		cols["leaf"] = Colors.green_d;
		cols["branch"] = this.truncColor;
		cols["elbowBranch"] = this.truncColor;
		cols["moss"] = Colors.white_l;
		cols["spike"] = Colors.red_l;
		cols["fruit"] = Colors.red_d;

	var colorFoliagePalette = (complex)? Colors[parameters.foliageColor] : Colors.getRandomFrom([Colors.pinks, Colors.yellows, Colors.greens, Colors.purples]);
  
	for (i=0; i&lt;this.attachsVerts.length; i++){
		var attDef = this.attachsVerts[i];
		var v = geom.vertices[attDef.index];
		var type = attDef.type;
		var col = cols[type];
		var attach, s, r, th;
		
		if (type == "moss"){
			s = Math2.rangeRandom(1,2);
			attach = new CustomMesh.SphereMesh(s,5,3, col, true);
			attach.geometry.applyMatrix(new THREE.Matrix4().makeScale(.6,1,.3));
			attach.quaternion.setFromUnitVectors ( new THREE.Vector3( 0, 0, 1 ), this.verticesNormals[attDef.index] );
		}else if (type == "spike"){
			s = Math2.rangeRandom(1,3);
			attach = new CustomMesh.SphereMesh(s,2,2, col, true);
			attach.geometry.applyMatrix(new THREE.Matrix4().makeScale(.1,1,.1));
			attach.quaternion.setFromUnitVectors ( new THREE.Vector3( 0, 1, 0 ), this.verticesNormals[attDef.index] )
		}else if(type == "fruit"){
			s = Math2.rangeRandom(2,4);
			attach = new Tomatoe(s, Colors.getRandomFrom(Colors.pinks, complex), Colors.getRandomFrom(Colors.greens)).mesh;
			attach.quaternion.setFromUnitVectors ( new THREE.Vector3( 0, 1, 0 ), this.verticesNormals[attDef.index] )
			//attach.rotation.z += Math.PI/4 + Math.random()*Math.PI/4;
		}else if(type == "leaf"){
			s = Math2.rangeRandom(1,2);
			attach = new Leaf(s,col).mesh;
			attach.quaternion.setFromUnitVectors ( new THREE.Vector3( 0, 1, 0 ), this.verticesNormals[attDef.index] )
			//attach.rotation.z += Math.PI/4 + Math.random()*Math.PI/4;

		}else if(type == "elbowBranch"){
			r = Math2.rangeRandom(this.truncHeight*.05,this.truncHeight*.15);
			th = Math2.rangeRandom(this.truncStartRadius*40/(1+v.y),this.truncStartRadius*60/(1+v.y));
			attach = new ElbowBranch(r,th,col, colorFoliagePalette, this.hierarchy+1, complex).mesh;
			attach.quaternion.setFromUnitVectors ( new THREE.Vector3( -1, 0, 0 ), new THREE.Vector3( v.x, 0, v.z ).normalize() );
		}else if(type == "branch"){
			s = Math2.rangeRandom(this.truncHeight*.03,this.truncHeight*.06);
			th = Math2.rangeRandom(this.truncStartRadius*.2,this.truncStartRadius*.4);
			attach = new Branch(s,th,col, colorFoliagePalette, this.hierarchy+1, complex).mesh;
			attach.quaternion.setFromUnitVectors ( new THREE.Vector3( 0, 1, 0 ), new THREE.Vector3( v.x, 0, v.z ).normalize() );
		}

		attach.position.copy(v);
		attach.userData.targetY = v.y;
		attach.userData.targetRotZ = attach.rotation.z;
		attach.userData.hierarchy = this.hierarchy+1;
		
		this.mesh.add(attach);
		attDef.mesh = attach;
	}
	geom.verticesNeedUpdate = true;
}

Trunc.prototype.kill = function(){
  var mesh = this.mesh;
  var geom = this.mesh.geometry;
	var l = geom.vertices.length;
  for (var i=0; i&lt;l; i++){
		var v = geom.vertices[i];
		TweenMax.killTweensOf(v);
	}
  killGrow(mesh);
  mesh = null;
}

function killGrow(mesh){
  for (var i=0; i&lt;mesh.children.length; i++){
		var child = mesh.children[i];
    TweenMax.killTweensOf(child.scale);
    TweenMax.killTweensOf(child.rotation);
		killGrow(child);
    child = null;
	}
}


Trunc.prototype.grow = function(){
	var scope = this;
	var geom = this.mesh.geometry;
	var l = geom.vertices.length;
	for (var i=0; i&lt;l; i++){
		var v = geom.vertices[i];
		var d = v.y/100;//Math.abs(this.truncHeight - v.y) /100;
		var s = 30/parameters.animationSpeed;// + (Math.abs(this.truncHeight - v.y)/100);
		TweenMax.from(v, s*.5, {x:0,z:0, delay:d*2, ease:Strong.easeInOut, onUpdate:scope.replaceAttachs, onUpdateScope:scope});
		TweenMax.from(v, s, {y:0, delay:d, ease:Strong.easeOut});
	}
	grow(this.mesh);
}

Trunc.prototype.replaceAttachs = function(){
	for (i=0; i&lt;this.attachsVerts.length; i++){
		var attDef = this.attachsVerts[i];
		var v = this.mesh.geometry.vertices[attDef.index];
		attDef.mesh.position.copy(v);
	}
	this.mesh.geometry.verticesNeedUpdate = true;
}

//Trunc.prototype.growAttachs = grow;

/*
BottleTrunc.prototype.updateWind = function(power){	
	this.mesh.rotation.z = (power/1000);
	for (var i=0; i&lt;this.mesh.children.length; i++){
		var child = this.mesh.children[i];
		child.rotation.z = child.userData.targetRotZ + Math.random()*power/1000;
	}
}
//*/

// BRANCH

ElbowBranch = function(radius, thickness, color, colorFoliagePalette, hierarchy, complex){
  this.type = "elbowBranch";
	var radSegs = (complex)?5:3;
	var tubSegs = (complex)?10:4;

	this.mesh = new CustomMesh.QuarterTorusMesh(radius,thickness,radSegs,tubSegs,Math.PI/2,color);
	this.mesh.geometry.applyMatrix(new THREE.Matrix4().makeTranslation(thickness,-thickness*2,0));
	this.mesh.userData.hierarchy = hierarchy;
  this.mesh.userData.refClass = this;

	var folThick = (complex)? parameters.foliageSize*(1+Math.random()*.5) : Math2.rangeRandom(8,24);
	this.attach = new Foliage(folThick, colorFoliagePalette, hierarchy+1,complex).mesh;
	
	this.attach.position.x = -radius;
	this.attach.position.y = radius - (thickness*3);
	this.mesh.add(this.attach);
}

Branch =function(h, thickness, color, colorFoliagePalette, hierarchy,complex){
  this.type = "branch";
	var radSegs = (complex)?5:3;
	
	this.mesh = new CustomMesh.CylinderMesh(thickness,thickness,h,radSegs, 1, color, false);
  this.mesh.geometry.applyMatrix(new THREE.Matrix4().makeTranslation(0,-1,0));
	this.mesh.userData.hierarchy = hierarchy;
  this.mesh.userData.refClass = this;

	var folThick = thickness*Math2.rangeRandom(3,8);
	this.attach = new Foliage(folThick, colorFoliagePalette, hierarchy+1,complex).mesh;
	this.attach.position.y = h-2;
	this.mesh.add(this.attach);
}

// FRUIT

Tomatoe = function(scale, colorFruit, colorLeaves,complex){
  this.type = "fruit";
	this.mesh = new THREE.Object3D();
  this.mesh.userData.refClass = this;
	this.core = new THREE.Object3D();

	this.stem = new Stem(scale, colorLeaves,complex);
	this.line = this.stem.mesh;

	var sw = (complex)?5:3;
	var sh = (complex)?5:3;
	
	this.fruit = new CustomMesh.SphereMesh(scale,sw,sh, colorFruit, false);
	this.fruit.position.y = 1;
	
	this.crown = new THREE.Object3D();

	var stepAngle = Math.PI*2 / 5;
	var crownCount = Math2.rangeRandomInt(3,6);
	for (var i=0;i&lt;5; i++){
    var leaf = new CustomMesh.DiamondMesh(scale,scale*1.5,.33,scale*.2,colorLeaves);
    leaf.geometry.applyMatrix(new THREE.Matrix4().makeRotationX(Math.PI/4));
    leaf.position.x = Math.cos( stepAngle*i)*.3;
    leaf.position.z = Math.sin( stepAngle*i)*.3;
    leaf.rotation.y = Math.PI/2 - stepAngle*i;
    this.crown.add(leaf);
  }
	this.core.position.x = this.stem.endPoint.x;
	this.core.position.y = this.stem.endPoint.y;
	this.core.position.z = this.stem.endPoint.z;
	this.core.quaternion.setFromUnitVectors ( new THREE.Vector3( 0, 1, 0 ), this.stem.lastDirection);
	this.core.add(this.crown);
	this.core.add(this.fruit);
	this.mesh.add(this.line);
	this.mesh.add(this.core);
}

// LEAF
Leaf = function(scale, color){
  this.type = "leaf";
	this.mesh = new THREE.Object3D();
  this.mesh.userData.refClass = this;
	this.core = new CustomMesh.DiamondMesh(scale*2,scale*3,.33,scale*.1,color);
	this.stem = new Stem(scale, color);
	this.line = this.stem.mesh;
	this.mesh.add(this.line);
	this.core.position.x = this.stem.endPoint.x;
	this.core.position.y = this.stem.endPoint.y;
	this.core.position.z = this.stem.endPoint.z;
	this.core.quaternion.setFromUnitVectors ( new THREE.Vector3( 0, 1, 0 ), this.stem.lastDirection);
	this.mesh.add(this.core);
}

// STEM
Stem  = function(scale, color, complex){
  this.type = "stem";
	this.lastDirection = new THREE.Vector3();
	this.endPoint = new THREE.Vector3();
	var linePoints = [];
	var sl = scale/50;
	var nHandlers = (complex)?6:3;
	var i, a=0, 
		tx = 0, ty=0, tz=0,
		pStartPoint = new THREE.Vector3(),
		v;
	for (i=0; i&lt;nHandlers; i++){
		v = new THREE.Vector3( tx, ty, tz );
		linePoints.push(v);
		if (i==nHandlers-2){
			pStartPoint.x = tx;
			pStartPoint.y = ty;
			pStartPoint.z = tz;
		}

		if (i&lt;nHandlers-1){
			tx += Math2.rangeRandom(-2,2);
			ty += sl*20;
			tz += Math2.rangeRandom(-2,2);	
		}else{
			this.endPoint.x = tx;
			this.endPoint.y = ty;
			this.endPoint.z = tz;
			this.lastDirection.subVectors( this.endPoint, pStartPoint )
		}
	}
	this.mesh =  CustomMesh.CurvedPath(linePoints, scale/10, color);
  this.mesh.userData.refClass = this;
}

// FOLIAGE

Foliage = function(scale, colorPalette, hierarchy,complex){
  
  this.type="foliage";
	var sw = (complex)? Math2.rangeRandomInt(3,10):Math2.rangeRandomInt(3,5);
	var sh = Math2.rangeRandomInt(3,6);
	var noise = (complex)? parameters.foliageNoise*scale : Math2.rangeRandom(scale/20,scale/5);
	this.colPalette = colorPalette;
	this.col = Colors.getRandomFrom(this.colPalette);
	this.scale = scale;
  
  
  this.mesh = new CustomMesh.SphereMesh(scale,sw,sh,this.col, false);
  this.mesh.userData.refClass = this;
	this.mesh.userData.hierarchy = hierarchy;
  
	var geom = this.mesh.geometry;
	geom.mergeVertices();
	var h = scale*2;
	var defAttachs;
  if (complex){
    defAttachs = [
			{type:"subFol", 	count : 6, 	minH : h*.2, 	maxH:h*.9, 	minAngle:0, 	maxAngle:0	},
		];  
  }else{
    defAttachs = [];
  }
	
	this.attachsVerts = GeometryHelpers.getAttachs(geom, defAttachs);

	GeometryHelpers.makeNoise(geom, noise);
  
  CustomMesh.flatshadeGeometry(geom);

	for (var i=0;i&lt;this.attachsVerts.length;i++){
		var attDef = this.attachsVerts[i];
		var v = geom.vertices[attDef.index];		
		var s = Math2.rangeRandom(scale*.05, scale*.2);
		var subFol = new SubFoliage(s, hierarchy+1).mesh;
    attDef.mesh = subFol;
		subFol.position.copy(v);
		subFol.rotation.z = Math2.rangeRandom(-Math.PI/8, Math.PI/8);
		subFol.rotation.x = Math2.rangeRandom(-Math.PI/8, Math.PI/8);
		this.mesh.add(subFol);
	}
	if (complex) foliagesComplex.push(this);
  else foliages.push(this);
}

SubFoliage = function(scale, hierarchy){
  this.type = "subfoliage";
	var sw = Math2.rangeRandomInt(2,4);
	var sh = Math2.rangeRandomInt(2,4);
	this.mesh = new CustomMesh.SphereMesh(scale,sw,sh,Colors.getRandomFrom(Colors.leaves), true);	
	this.mesh.userData.hierarchy = hierarchy;
  this.mesh.userData.refClass = this;
}

Foliage.prototype.launchParticle = function(){
  var p;
	var col = Colors.getRandomFrom(this.colPalette);
	if (waitingParticles.length){
		p = waitingParticles.pop();
		p.material.color.setHex(col);
	}else {
		p = new FlyingParticle(col, this.scale);
	}
	p.visible = true;
	p.scale.x = p.scale.y = p.scale.z = this.scale/20;
	p.userData.speedX = Math2.rangeRandom(1,3);
	p.userData.speedY = Math2.rangeRandom(.5,1);

	var vIndex = Math.floor(Math.random()*this.mesh.geometry.vertices.length);
	var pos = this.mesh.geometry.vertices[vIndex].clone();
	pos = this.mesh.localToWorld( pos );
	p.position.copy(pos);
	flyingParticles.push(p);
	scene.add(p);
}

Foliage.prototype.grow = function(){
  console.log("grow foliage");
	var scope = this;
	var geom = this.mesh.geometry;
	var l = geom.vertices.length;
	for (var i=0; i&lt;l; i++){
		var v = geom.vertices[i];
		var d =  Math.random()*.5 + v.y/25;
		var s = Math.random() + 20/parameters.animationSpeed;
    var sx = Math2.rangeRandom(-2,2);
    var sy = Math2.rangeRandom(-2,2);
    var sz = Math2.rangeRandom(-2,2);
		TweenMax.from(v, s, {x:0,z:0, y:0, delay:d, ease:Strong.easeInOut, onUpdate:scope.replaceAttachs, onUpdateScope:scope});
  }
	grow(this.mesh);
}

Foliage.prototype.replaceAttachs = function(){
	for (i=0; i&lt;this.attachsVerts.length; i++){
		var attDef = this.attachsVerts[i];
		var v = this.mesh.geometry.vertices[attDef.index];
		attDef.mesh.position.copy(v);
	}
	this.mesh.geometry.verticesNeedUpdate = true;
}

FlyingParticle = function(color){
	var mesh;
	var s = Math2.rangeRandom(1,4);
	var segs = Math2.rangeRandomInt(3,5);
	var segs2 = Math2.rangeRandomInt(2,5);
	
	if (Math.random()&lt;.25){
		mesh = new CustomMesh.TriMesh(s,s,.2,color,"top");
	}else if (Math.random()&lt;.5){
		mesh = new CustomMesh.RegPolyMesh(s,segs,1,color,false);
	}else if (Math.random()&lt;.75){
		mesh = new CustomMesh.SphereMesh(s,segs,segs2,color,false);
	}else{
		mesh = new CustomMesh.CylinderMesh(0,s,s,segs, 1, color,true);
	}
	return mesh;
}


function grow(mesh){
	//console.log("new grow");
	for (var i=0; i&lt;mesh.children.length; i++){
		var child = mesh.children[i];
    if (child.userData.refClass && child.userData.refClass.type == "foliage"){
      child.userData.refClass.grow();
    }else{
      var d = (child.position.y / 200) + child.userData.hierarchy;
      var s = 10+child.userData.hierarchy*2;
      s = s/parameters.animationSpeed;
      TweenMax.from(child.scale, s, {x:0.01, y:0.01, z:0.01, delay:d, ease:Back.easeInOut});
      TweenMax.from(child.rotation, s, {x:0, y:0, z:0, delay:d, ease:Back.easeInOut});
      grow(child);  
    }
	}
}

window.addEventListener('load', init, false);

function init(event){
  createStats();
  initCore();
  initGUI();
  createLights();
  createFloor();
  createForest();
  createTree();
  loop();
}

function updateShadows(){
  scene.traverse( function ( object ) {
    if ( object instanceof THREE.Mesh ) {
      object.castShadow = true;
      object.receiveShadow = true;
    }
  });
}

function createStats(){
  // STATS
  stats = new Stats();
  stats.setMode( 0 ); // 0: fps, 1: ms, 2: mb
  // align top-left
  stats.domElement.style.position = 'absolute';
  stats.domElement.style.left = '0px';
  stats.domElement.style.top = '0px';
  document.body.appendChild( stats.domElement );
}

function loop(){

  stats.begin();
  
  console.log("waiting",waitingParticles.length);

  var frustum = new THREE.Frustum();
  frustum.setFromMatrix( new THREE.Matrix4().multiplyMatrices( camera.projectionMatrix, camera.matrixWorldInverse ) );  
  
  //*
  if (Math.random()>.5){
    var fol = foliages[Math.floor(Math.random()*foliages.length)];
    fol.launchParticle();
  }
  
   if (Math.random()>.9){
    var fol = foliagesComplex[Math.floor(Math.random()*foliagesComplex.length)];
    fol.launchParticle();
  }
  
  for (var i=0; i&lt;flyingParticles.length; i++){
    var p = flyingParticles[i];
    p.position.x += p.userData.speedX + Math.random()/10;
    p.position.y += p.userData.speedY + Math.random()/20;
    
    p.rotation.x += .01 + Math.random()/100;
    p.rotation.y += .01 + Math.random()/10;
    p.rotation.z += .1 + Math.random()/20;

    if(!frustum.containsPoint( p.position )){
      p.visible = false;
      waitingParticles.push(flyingParticles.splice(i,1)[0]);
    }
  }
  //*/
  render();
  stats.end();
  requestAnimationFrame(loop);
}

</pre></div>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/583566769?h=5ae16cdf3e&title=0&byline=0&portrait=0" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/dnV-O6gC3jY" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="504" src="https://www.youtube.com/embed/q-yYwKYqtsU" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="500" src="https://www.youtube.com/embed/p578E7tC9EA" title="YouTube video player" frameborder="0" allowfullscreen></iframe>

<a href="https://solecollector.com/"> <em>##SOUL_COLLECTOR_IS_IN_THE_BUILDING</em></a>
 <div class='row'>
    <div class='column'>
      <div class='blue-column'>
        <img src="https://images.solecollector.com/complex/images/c_crop,h_893,w_1074,x_3,y_75/c_fill,dpr_2.0,f_auto,fl_lossy,q_auto,w_800/oivtkfz2vwgpdfzccpwr/air-jordan-4-retro-infrared-dh6927-061-pair" alt="Girl in a jacket" >
      </div>
    </div>
    <div class='column'>
      <div class='green-column'>
        <img src="https://images.solecollector.com/complex/images/c_crop,h_893,w_1074,x_3,y_75/c_fill,dpr_2.0,f_auto,fl_lossy,q_auto,w_800/oivtkfz2vwgpdfzccpwr/air-jordan-4-retro-infrared-dh6927-061-pair" alt="Girl in a jacket" >
      </div>
    </div>
    </div>	
  </div>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/juqws1LIH-I" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="500" height="315" src="https://www.youtube.com/embed/2klTw123_jw" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="500" src="https://www.youtube.com/embed/TwYz5iI7pm0" title="YouTube video player" frameborder="0"allowfullscreen></iframe>
<iframe width="333" height="315" src="https://www.youtube.com/embed/_Hcl-oA6bfk" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="444" src="https://www.youtube.com/embed/K_ovAyxoriE" frameborder="0" title="YouTube video player" allowfullscreen></iframe>
 <div class='row'>
    <div class='column'>
      <div class='blue-column'>
        <img src="https://i.pinimg.com/564x/65/5b/a4/655ba4cb6e341f9fda1a7bdddd2077df.jpg" alt="Girl in a jacket" >
      </div>
    </div>
    <div class='column'>
      <div class='green-column'>
        <img src="https://i.pinimg.com/564x/b9/ee/08/b9ee0813b77317a011c579c1474adb83.jpg" alt="Girl in a jacket" >
      </div>
    </div>
 <div class='column'>
      <div class='blue-column'>
        <img src="https://i.pinimg.com/564x/59/8c/52/598c5256f48e182e0dd034e2f8e875ae.jpg" alt="Girl in a jacket" >
      </div>
    </div>	
  </div>
<iframe width="100%" height="400" src="https://www.youtube.com/embed/6Vi-o09XpYQ" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/ai55ujNrF_w" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<div class='some-page-wrapper'>
  <div class='row'>
    <div class='column'>
      <div class='blue-column'>
        <img src="https://i.pinimg.com/564x/8a/6f/62/8a6f6232a31191619856168f186f0904.jpg" alt="Girl in a jacket" >
      </div>
    </div>
    <div class='column'>
      <div class='green-column'>
        <img src="https://i.pinimg.com/564x/8a/6f/62/8a6f6232a31191619856168f186f0904.jpg" alt="Girl in a jacket" >
      </div>

    </div>
  </div>
	  <div class='row'>
    <div class='column'>
      <div class='blue-column'>
        <img src="https://i.pinimg.com/564x/8a/6f/62/8a6f6232a31191619856168f186f0904.jpg" alt="Girl in a jacket" >
      </div>
    </div>
    <div class='column'>
      <div class='green-column'>
        <img src="https://i.pinimg.com/564x/8a/6f/62/8a6f6232a31191619856168f186f0904.jpg" alt="Girl in a jacket" >
      </div>

    </div>
  </div>
</div>



<iframe width="100%" height="400" src="https://www.youtube.com/embed/flK2tqusitk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<iframe width="100%" height="500" src="https://www.youtube.com/embed/stuySQv7qw4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<a href="https://www.deviantart.com/sachsen">##CHECK_OUT_SACHSEN_ON_DEVIANT_ART</a> <em>Try to click on it.</em>
  <div class='row'>
    <div class='column'>
      <div class='blue-column'>
        <a href="https://www.deviantart.com/sachsen/art/Afro-Brain-114793112"><img src="https://i.pinimg.com/564x/0c/3e/33/0c3e3331ea6f7c6fe47d8d200b7ff47d.jpg" alt="##TO_MY_DEAR_SELASSIE_WOMEN##SARTU##SAATU#MUNA##QUBUXE##LAHLEEBELLAH##SUMMER_and_HEATHER##BHATI##CYNTHIA_and_VAL_wit_DA_BREAD_IN_DAH_OVEN!" ></a>
      </div>
    </div>
    <div class='column'>
      <div class='green-column'>
        <a href="https://www.deviantart.com/sachsen/art/Afro-Brain-114793112"><img src="https://i.pinimg.com/564x/0c/3e/33/0c3e3331ea6f7c6fe47d8d200b7ff47d.jpg" alt="##TO_MY_DEAR_SELASSIE_WOMEN##SARTU##SAATU#MUNA##QUBUXE##LAHLEEBELLAH##SUMMER_and_HEATHER##BHATI##CYNTHIA_and_VAL_wit_DA_BREAD_IN_DAH_OVEN!" ></a>
      </div>
    </div>
  </div>
</div>
<iframe width="100%" height="400" src="https://www.youtube.com/embed/6ArSfXnm2c0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<div class='some-page-wrapper'>
  <div class='row'>
    <div class='column'>
      <div class='blue-column'>
        <img src="https://i.pinimg.com/564x/df/7e/8c/df7e8c8a4889b261be9d9da5ae00d9fb.jpg" alt="Girl in a jacket" >
      </div>
    </div>
    <div class='column'>
      <div class='green-column'>
        <img src="https://i.pinimg.com/564x/df/7e/8c/df7e8c8a4889b261be9d9da5ae00d9fb.jpg" alt="Girl in a jacket" >
      </div>
    </div>
  </div>
</div>

<iframe width="100%" height="400" src="https://www.youtube.com/embed/ZmPfxMBNilg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<iframe width="100%" height="457" src="https://www.youtube.com/embed/QzK-fn9NaCE" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="450" src="https://www.youtube.com/embed/ZpIkc7KlqZw" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/4I3CovIKJWE" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<div class='some-page-wrapper'>
  <div class='row'>
    <div class='column'>
      <div class='blue-column'>
        <img src="https://akns-images.eonline.com/eol_images/Entire_Site/2017107/rs_1080x1080-171107190450-23279723_777542925770459_8932444824968101888_n.jpg?fit=around%7C1080:1080&output-quality=90&crop=1080:1080;center,top" alt="Girl in a jacket" >
      </div>
    </div>
    <div class='column'>
      <div class='green-column'>
        <img src="https://i.pinimg.com/564x/87/c2/37/87c237ef7511042953d3d58f8af4d6c8.jpg" alt="Girl in a jacket" >
      </div>
    </div>
  </div>
<div class='row'>
	<iframe width="100%" height="315" src="https://www.youtube.com/embed/7XLW5CvDQ7E" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
	<iframe width="100%" height="500" src="https://www.youtube.com/embed/V54CEElTF_U" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
	<iframe width="100%" height="500" src="https://www.youtube.com/embed/tCXGJQYZ9JA" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
	</div>
</div>

<iframe width="100%" height="315" src="https://www.youtube.com/embed/4t649hEMbIA" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/MGBGdtoupJU" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<script src="https://gist.github.com/ThakaRashard/464f6645a69d82bdfe6a8dc224fe0f3d.js"></script>
<div class='some-page-wrapper'>
  <div class='row'>
    <div class='column'>
      <div class='blue-column'>
        <img src="https://thakarashard.github.io/hole_to_another_universe_blog/img/future-the-wizrd.jpg" alt="Girl in a jacket" >
      </div>
    </div>
    <div class='column'>
      <div class='green-column'>
        <img src="https://thakarashard.github.io/hole_to_another_universe_blog/img/future-the-wizrd.jpg" alt="Girl in a jacket" >
      </div>
    </div>
  </div>
<div class='row'>
	<iframe width="100%" height="315" src="https://www.youtube.com/embed/wlASYNwGo9E" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
	</div>
</div>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/lehBlK2MrD8" title="YouTube video player" allowfullscreen frameborder="0"></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/AWVd-UHov0Q" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/apf2KPgBoSM" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/d3bvmzEW4T0" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/aH3VTCTUw_4" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/z9F-jdqi5jQ" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/XzQMn5Tm8gM" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/0TBkSRPDXME" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<a href="https://babysizer.com/?ref=discuvver" > ##BABYSIZER##Quite_well_designed_the_coupons-fuck_us_up-tho </a>
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="WNZxOOx" data-editable="true" data-user="cjgammon" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/cjgammon/pen/WNZxOOx">
  gradient mesh</a> by CJ Gammon (<a href="https://codepen.io/cjgammon">@cjgammon</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="GRMqwdK" data-editable="true" data-user="Calleb" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Calleb/pen/GRMqwdK">
  UFO with Ease (codepenchallenge)</a> by Calle (<a href="https://codepen.io/Calleb">@Calleb</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
<p class="codepen" data-height="300" data-theme-id="dark" data-default-tab="css,result" data-slug-hash="dpZVOr" data-editable="true" data-user="luke__duncan" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/luke__duncan/pen/dpZVOr">
  HTML5 Audio Player</a> by Luke Duncan (<a href="https://codepen.io/luke__duncan">@luke__duncan</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
<p><a href="https://vimeo.com/153849913">Surfing Stockshots</a> from <a href="https://vimeo.com/timbonython">Tim Bonython</a> on <a href="https://vimeo.com">Vimeo</a>.</p>
<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/651386804?h=79c650eb04" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<p><a href="https://vimeo.com/651386804">Takeover</a> from <a href="https://vimeo.com/newyorktimes">The New York Times</a> on <a href="https://vimeo.com">Vimeo</a>.</p>
<p><a href="https://vimeo.com/651386804">Takeover</a> from <a href="https://vimeo.com/newyorktimes">The New York Times</a> on <a href="https://vimeo.com">Vimeo</a>.</p>
<p><a href="https://vimeo.com/651386804">Takeover</a> from <a href="https://vimeo.com/newyorktimes">The New York Times</a> on <a href="https://vimeo.com">Vimeo</a>.</p>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/-RbSogwKY94" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/esQXF9UGFw0" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/F4_3TO7jH04" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/LMkJZqVnx0s" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/XHrskkHf958" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/GAWHzGNcTEw" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/ScMJrK5bQDg" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
##THiS_iS_LOS_ANGELES
<iframe width="100%" height="315" src="https://www.youtube.com/embed/n3ceoeubxxQ" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/hkygiqC7ulQ" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/7Ldil3a7Y3g" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/bPrBzreWZW0" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
### Deazeer! PORNHUB##WHERE_ARE_MY_WIVES##A_HOTEL_IN_LANCASTER?!##
<iframe width="100%" height="315" src="https://www.youtube.com/embed/8HAcOSc_aGI" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/K4XAwlYdSlA" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/DqDeH3hwxfw" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<li><a href="https://www.rferl.org/a/exiled-jehovahs-witness-i-dont-know-what-the-russian-government-is-doing-/29917297.html">1 # Exiled Jehovah's Witness: 'I Don't Know What The Russian Government Is Doing'</a>  
	![image](https://user-images.githubusercontent.com/93835618/145619309-c586a8c5-0759-422b-a02a-25186dab3289.png)

<iframe width="100%" height="315" src="https://www.youtube.com/embed/U_tyfMUSGo4" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/b-7-mgnseB8" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/gJktf4aTNvk" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/HbqQL0J_Vr0" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
	<a href="https://vimeo.com/396000267" target="_blank" >WHiTESUPREMACY</a><a href="https://vimeo.com/396000267" target="_blank" >WHiTESUPREMACY</a> <a href="https://vimeo.com/396000267" target="_blank" >WHiTESUPREMACY</a><a href="https://vimeo.com/396000267" target="_blank" >WHiTESUPREMACY</a>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/bJ9r8LMU9bQ" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/p-xXGVsYOyM" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/yCmxcHJapCA" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/OTnH3zs8wRo" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/zJBC8L3pG_Y" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.youtube.com/embed/kuDuDKvV2Mw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<iframe width="560" height="315" src="https://www.youtube.com/embed/qi2lPz2F3vI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<iframe width="100%" height="450" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/playlists/249959909&color=%2300ff01&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/kevingates" title="Kevin Gates" target="_blank" style="color: #cccccc; text-decoration: none;">Kevin Gates</a> · <a href="https://soundcloud.com/kevingates/sets/islah-6" title="Islah (Deluxe)" target="_blank" style="color: #cccccc; text-decoration: none;">Islah (Deluxe)</a></div>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/sj9q5ve6bh0" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/Hr4wz4-27PY" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/QlD_0iQr0nU" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
<h2 class="neonText"> Its been 563 days since I have seen our daughter ##CORAL_IRIS_KELLY. </h2> 
Her mother mother Erika Renee Kelly was kidnapped on Feb 2,2020. A local Atlanta Matt Field bragged about it on Facebook stating "I_SOLD_HER. I found her near Venice beach California and my tattooist Kennie_Davis of ##Jolly_Roger_Tattoo in _Stockbridge#Georgia was not too far from the scene. Erika and I were not estranged when she disappeared as [ESSENCE_MAGAZiNE_STATED](https://www.essence.com/news/erika-kelly-missing-atlanta-georgia/) we were coparenting. I was laid off from my IT job at [Ionic Security](https://www.linkedin.com/company/ionic-security) after my work was repeatedly sabotaged by my manager. I opened a case with ##Fulton_County_Family_Services two months before our eviction from our ##East_Atlanta_Home_at_631_Moreland_Ave_in_Atlanta_Georgia they failed to process us after repeated visits and calls. I took odd jobs and even scored a mural gig with [Mercedes_BenZ_Stadium](https://mercedesbenzstadium.com/) for the [Atlanta_Falcons](https://www.atlantafalcons.com/). They paid me $1500 for a 40ft graffiti mural on red canvas for former athlete ##Deion_Sanders. I was severely underpaid but it covered the rent for one more month. I moved in with Constancia and her daughter ##Akeeva, got Coral in school at [Chapel Hill Elementary](https://www.chapelhilles.dekalb.k12.ga.us/) and worked hard to get a new 9-5.
 
Constancia did not like me or Coral living with her and Akeeva so they undercut me with accusations of erratic behavior and started thier own dfacs case accusing me of schizophrenia. I had no income and was repeatedly denied foodstamps and welfare by a woman named ##DANIELLE_MASHONGA_and_her_colleage##MANESSA_WARNER... ##Coral would ask <h2>##Where_is_mommy?!?</h2>I told her that Matt stole and raped her and she needs our help, so we have to keep looking. Constancia and Akeeva constantly defended Matt. He is a known pedophile and child and adult rapist in the Atlanta art community. I did not know this. We shopped at the same record store and he often offered me work. I loath rapist. I loath pedophilia. Once I learned of his ways I distanced myself. So ##Erikas_mother_and_sisters_DEFENDING_HIM, struck me as bizarre. "##Its_just_a_white_boy_joke##He_didnt_sell_her. [DFACS](https://dfcs.georgia.gov/) stalked me on Facebook and indirectly accused me of ##CHILD_MOLESTATION for a video where we were playing with a wand style muscle massager, it was innocent.  They [forcibly removed Coral](https://www.youtube.com/watch?v=AmYdIZhahrQ) saying that I was saying ["inappropriate things"](https://www.youtube.com/watch?v=9sCE3HhjSbY) and violating her by saying that her mom had been raped and kidnapped. I learned that telling Coral the ugly truth was the best way to keep a solid trust filled relationship with her.
 
In the DFACS meeting, puzzled I told Mashonga the truth, I cant find work, my reputation was being sabotaged and I could not even get a job at ##Kroger the local grocery store. I told Mashonga I needed money for food, Constancia would not feed niether me or Coral. I asked Mashonga in [This_Family_Meeting](https://www.youtube.com/watch?v=Q8NXhT6_Tx8) if she cared about me dying on the street and she shook her head, no. I was never interviewed with Coral at all, I never got a psych eval until I got to a ##UCLA_Recoup_Center_in_PalmDale_California.
 
In early October I saw Coral, in Pasadena, ##California, with a grown man wearing fishnet stockings... Shes 9. I was shot with a poison dart one day later, my skateboard stolen and my foot began to swell larger that a shoe could fit... I was rushed to the emergency room and ##UCLA ##Cut_my_foot_to_the_bone_to_drain_the_infection... I cant run any more and am now handicapped
<iframe width="100%" height="315" src="https://www.youtube.com/embed/Q8NXhT6_Tx8" title="YouTube video player" frameborder="0" ></iframe>



<iframe width="100%" height="400" src="https://www.youtube.com/embed/9sCE3HhjSbY" title="YouTube video player" frameborder="0" llowfullscreen></iframe>
<iframe width="100%" height="400" src="https://www.youtube.com/embed/AmYdIZhahrQ" title="YouTube video player" frameborder="0" allowfullscreen></iframe>

<h2>Her_Former_Life_With_Me</h2>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/-oZuyrU764s" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/CsM4jNSAm4A" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/ydGxlS8l7Y0" title="YouTube video player" frameborder="0" allowfullscreen></iframe>

<iframe width="100%" height="315" src="https://www.youtube.com/embed/F5Qx4Y_hUuE" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/iooViITRp9M" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/NYOQDnWFXYI" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/0vafNHo3GuQ" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/-9aqK0nCPPk" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/MOwP-woHsnw" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/K4XAwlYdSlA" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="300" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/1147966270&color=%23ff5500&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true&visual=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/tycho" title="Tycho" target="_blank" style="color: #cccccc; text-decoration: none;">Tycho</a> · <a href="https://soundcloud.com/tycho/only-love-with-brijean" title="Only Love (with Brijean)" target="_blank" style="color: #cccccc; text-decoration: none;">Only Love (with Brijean)</a></div>
	 <iframe width="100%" height="315" src="https://www.youtube.com/embed/i-UXy-b8TaU" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/K_O4BrwHWH4" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/I379EECFVoM" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/I379EECFVoM" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/_wIci7ZseRA" title="YouTube video player"  allowfullscreen frameborder="0" ></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/kGDhHxgY6uo" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/_11uQVI21mQ" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/r-Nw7HbaeWY" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/zsb1dgsFvpM" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/SJuFdkMOP20" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="80%" height="315" src="https://www.youtube.com/embed/5eysL68IoTI" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="60%" height="315" src="https://www.youtube.com/embed/TwYz5iI7pm0" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="70%" height="315" src="https://www.youtube.com/embed/Qd176cCPJRs" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
<iframe width="80%" height="315" src="https://www.youtube.com/embed/ssVpXj9dOB4" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="90%" height="315" src="https://www.youtube.com/embed/sSHzosSNjbM" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/KHDOj2QxAfQ" title="YouTube video player" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/Pdp7vNmhwuw" frameborder="0" ></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/qy2D66L8lBw" title="##JAYDA_G_IS_IN_PROSTITUTION##I_WAS_KIDNAPPED##DAT_WAZ_JAYDA" frameborder="0" allowfullscreen></iframe>
<iframe width="100%" height="315" src="https://www.youtube.com/embed/yiSTcdi82S0" title="YouTube video player" frameborder="0"  allowfullscreen></iframe>
<iframe width="100%" height="300" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/511197930&color=%231eff00&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true&visual=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/littledragon" title="Little Dragon" target="_blank" style="color: #cccccc; text-decoration: none;">Little Dragon</a> · <a href="https://soundcloud.com/littledragon/lover-chanting" title="Lover Chanting" target="_blank" style="color: #cccccc; text-decoration: none;">Lover Chanting</a></div>
<iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/542645481&color=%231eff00&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/littledragon" title="Little Dragon" target="_blank" style="color: #cccccc; text-decoration: none;">Little Dragon</a> · <a href="https://soundcloud.com/littledragon/lover-chanting_jayda-g-remix" title="Lover Chanting (Jayda G Remix)" target="_blank" style="color: #cccccc; text-decoration: none;">Lover Chanting (Jayda G Remix)</a></div>
<a href="https://youtu.be/R2rct18-iSM" target="_blank">
<img src="https://previews-te.wetransfer.net/file/wetransfer/j1oc/sx7o7n0024o62tetf20211209185240/sfnjkna05umtp18ng20211209203353?height=2048&source=spaceship&width=2048&s=c2447d9751e86f043f5382d310516d51daeacf2c&Expires=1639085661&Signature=cn9UJSzK5KY117oGH7W-f8hEDJQuQ2-44NXG8b06Jkc63lRkAmezfU~X3Pd-tJaB2a9JGKBOfIPYyw7nzQTzEGfg70LeJw3PzsWBuO6J6miNOzZ2rQkArS42BJg1N7s-8FOld3X~RK1Qp94iUtSh~74RMhqdZlA08BgDkR4Ktn11TIDYEV~E-zeOlNQWeurMSzsnOgX0ldCYvOinaTNNN-5Jc-6aDh-WSYWy8cu-lM6yOTAPxzy-fkeQ66GGq25PoNKBfhXa25kQytCOM2EaeHqlNbCuEB5yn8LE32HoqsLWch0VmgFIsJDsGGWxst0c2ePQ8C6tSl9khPC-k8~Kgg__&Key-Pair-Id=APKAIRLQFERKGUWFG7GQ" alt="an image" title="The title of this image"/>
  </a>
  <a href="https://youtu.be/hiFcIHGWEoA" target="_blank">
<img src="https://previews-te.wetransfer.net/file/wetransfer/p1oc/sx7o7n0024o62tetf20211209185240/sqhqb6utjxe38qgr920211209204127?height=2048&source=spaceship&width=2048&s=617c137d21b7ba5d6ec7b66f8be27f007d12b87d&Expires=1639086148&Signature=Xh1bE3ypIDs1Z0fmxwTTZDxd-wPARlXc8B1NmGtSx2Irxu8bD~-Z4cR0aJbg6aLRvXSr1BdFySgKzz5HGCzogsZTrCkNrDMhr3Sg3wPqDd3h0uPQflqHUlduZI-tajdLK4~T5ksn~IdAyPPdMXjUrPmgLMC8oXk1Fzp-4Q-Uyh198PmZjk28FoGwI53uotvxlG8WuIeW4uudUbil-M3jmABdw2e8B6TbyedJdD-APCT54va2p78~PAY0EAOeFKV2nR~DTu9Z-N6Ef0Hig7XPaZ8LDhQmH0im8Hyng3iktwTMUSNyLqQCzDuROqxpRTXzRBauqZmJfkN9BMejm27kOg__&Key-Pair-Id=APKAIRLQFERKGUWFG7GQ" alt="an image" title="The title of this image"/>
  </a>

<p class="codepen" data-height="300" data-theme-id="dark" data-default-tab="css,result" data-slug-hash="prMyrO" data-editable="true" data-user="morimiko" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/morimiko/pen/prMyrO">
  Accordion Menu + Tooltip</a> by mori (<a href="https://codepen.io/morimiko">@morimiko</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
<p class="codepen" data-height="300" data-theme-id="dark" data-default-tab="css,result" data-slug-hash="NoKOrE" data-editable="true" data-user="liquidcharcoal" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/liquidcharcoal/pen/NoKOrE">
  CSS Only Accordion Menu</a> by PARTH PATEL (<a href="https://codepen.io/liquidcharcoal">@liquidcharcoal</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
<p class="codepen" data-height="300" data-theme-id="dark" data-default-tab="css,result" data-slug-hash="QPvjQJ" data-editable="true" data-user="rssabbir" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/rssabbir/pen/QPvjQJ">
  Amazing accordion menu using only HTML &amp; CSS</a> by Rs Sabbir Ahmed (<a href="https://codepen.io/rssabbir">@rssabbir</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
<div id="box-shadow"> 
<p class="codepen" data-height="300" data-theme-id="dark" data-default-tab="css,result" data-slug-hash="aOoBXq" data-editable="true" data-user="samarkandiy" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/samarkandiy/pen/aOoBXq">
  Animate sprite with CSS</a> by Avaz Bokiev (<a href="https://codepen.io/samarkandiy">@samarkandiy</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
  </div>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
<iframe id="reddit-embed" src="https://www.redditmedia.com/r/IdiotsInCars/comments/rcaitc/new_to_the_sub_thought_id_enter_with_a_banger/?ref_source=embed&amp;ref=share&amp;embed=true&amp;theme=dark" sandbox="allow-scripts allow-same-origin allow-popups" style="border: none;" height="620" width="100%" scrolling="no"></iframe>
<amp-iframe width=100% height=620 sandbox="allow-scripts allow-same-origin allow-popups allow-popups-to-escape-sandbox" layout="responsive" resizable frameborder="0" src="https://www.redditmedia.com/r/IdiotsInCars/comments/rcaitc/new_to_the_sub_thought_id_enter_with_a_banger/?ref_source=embed&amp;ref=share&amp;embed=true&amp;theme=dark"> <amp-img layout="fill" src="https://rebed.redditmedia.com/assets/03657792c480fd6bbb7bef821c859742.svg" placeholder></amp-img> <div overflow>Click to expand</div> </amp-iframe>
![DREEZY_IS_HIS_WIFE](https://previews-te.wetransfer.net/file/wetransfer/p1oc/sx7o7n0024o62tetf20211209185240/sjzxd9o4v1b8x4pbh20211209191816?height=2048&source=spaceship&width=2048&s=e898eadaf2e90a6453b4e4cbd3b3ca3e5a67f8b9&Expires=1639081101&Signature=gUqZ2nQT9AKhOkEhyhRIcNqv660GLaaX~fV1PKJconQndLf4wCn7t7C2SDpAof4UjYgsmgvocIvcHtl60XPDsRWox3cKI3dqB0VRgCMJAKqCxmK1TLzzX3K2mexfmiUjj~KhFQ2CvQrqwAP34BfM99PZG0BRbPmPtGxdRGSfjhcte9jpTRR-ID8Mu2Eu7nZvO80~G7dBy9lOCpSUhvbZt1ji4ZZcVFUugIPf-A3yciSWAmTd8-DGOrPyRyEw-w-m0wc8nY2d~iOPyF7ZnbZjyuQ6fQbe6p2m3AvqxJ5wnasqgg3jgcWO4cCIa539F~Rp-djjg9Z42aOGp2PzofrViw__&Key-Pair-Id=APKAIRLQFERKGUWFG7GQ)
<iframe height="300" style="width: 100%;" scrolling="no" title="Pure CSS 3D Synthesizer (mousedown for rotation)" src="https://codepen.io/suez/embed/GJKRPN?default-tab=css%2Cresult&editable=true" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/suez/pen/GJKRPN">
  Pure CSS 3D Synthesizer (mousedown for rotation)</a> by Nikolay Talanov (<a href="https://codepen.io/suez">@suez</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>
<img src="https://previews-te.wetransfer.net/file/wetransfer/p1oc/sx7o7n0024o62tetf20211209185240/s5h3kpkljjeo4134l20211209185320?height=2048&source=spaceship&width=2048&s=7c2d8359b221cc60d37994c95878ff3e98537aac&Expires=1639079610&Signature=gzehJ~JE8AD1B8490aoh37~af0IyNGj4htu~qFgBg8b5NmJoS-FWWZyEcVMBL4PHOAuy27WjrD~wqBIb0ozmB0a5E3DSOg-8veRlmaqGo~IINLMG1BqHtUmWu0SlZSawoDGL5n5Qv80qpiWA~C1Ggnr9v6Dj23s54Gdc~v56XYj~Xiea-DyGPvLu0cwsjGy9bnAfvbIPrOzCgi0e0i1P7tD9ABz1C3BKFlxnfPpRlXQhBqZMAoLm6QXzrri1WgkEG5yWrQ-W3bIhyLY7Fh9A~tltHQxhCmR8rTNXi8-qhnB52pA~9mD-Sy8moizSaW1evJX1in~fEHPTQZnwMH8IDA__&Key-Pair-Id=APKAIRLQFERKGUWFG7GQ" >
<h2 class="neonText"> EDiTABLE_on_TOP## </h2>
<p class="codepen" data-height="300" data-default-tab="css,result" data-slug-hash="lEDBj" data-editable="true" data-user="Rplus" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Rplus/pen/lEDBj">
  [PURE CSS] border animation without svg</a> by Rplus (<a href="https://codepen.io/Rplus">@Rplus</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="lEDBj" data-user="Rplus" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Rplus/pen/lEDBj">
  [PURE CSS] border animation without svg</a> by Rplus (<a href="https://codepen.io/Rplus">@Rplus</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>


<article>
  <pre class="candybox2">           ________
      _,.-Y  |  |  Y-._
  .-~"   ||  |  |  |   "-.
  I" ""=="|" !""! "|"[]""|     _____
  L__  [] |..------|:   _[----I" .-{"-.
 I___|  ..| l______|l_ [__L]_[I_/r(=}=-P
[L______L_[________]______j~  '-=c_]/=-^
 \_I_j.--.\==I|I==_/.--L_]
   [_((==)[`-----"](==)j
      I--I"~~"""~~"I--I
      |[]|         |[]|
      l__j         l__j
      |!!|         |!!|
      |..|         |..|
      ([])         ([])
      ]--[         ]--[
      [_L]         [_L]
     /|..|\       /|..|\
    `=}--{='     `=}--{='
   .-^--r-^-.   .-^--r-^-.
</pre>
  
</article>
## HOW_DO_YOU_POST##

![##JUiCY_J_STAY_TRiPPY_IMAGE_TAKEN_FROM_DiSCOGS](https://pixelfed-tokyo.sgp1.digitaloceanspaces.com/public/m/_v2/362683957004104159/4f8b684e5-e9314a/fXulQ42j0vcu/4BhlKL2x3VAUETOiIIfEhGNtZefX9o0witXLjFGq.jpg)


â€œEverything should be done in love.â€ â€” 1 Corinthians 16:14

## Welcome to GitHub Pages
  </body>
  </html>

You can use the [editor on GitHub](https://github.com/ThakaRashard/Hole_To_Another_UNiVERSE_BLOG/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/ThakaRashard/Hole_To_Another_UNiVERSE_BLOG/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and weâ€™ll help you sort it out.
	

## #!/usr/bin/ruby -w --debug
#ONE_DAY_MY_BLOG_WiLL_RETURN TRUE when run from the command line
{% highlight ruby %}
1 # HOLE_TO_ANOTHER_UNiVERSE##############################
2 # TO####################################################
3 # ANOTHER###############################################
4 # UNiVERSE##############################################
{% endhighlight %}

