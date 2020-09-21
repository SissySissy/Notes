
# 3JS

## Set up html
Connect the three cdn libraries, download the GLTFLoader.js  

Load node and download http-server: 

    "scripts": {
        "start":"http-server",
        "test": "echo \"Error: no test specified\" && exit 1"
      },

 @author Rich Tibbett / https://github.com/richtr

    <html>
    	<head>
    		<title>My first three.js app</title>
    		<style>
    			body { margin: 0; }
    			canvas { width: 100%; height: 100%; }
    		</style>
    		<script src="https://cdnjs.cloudflare.com/ajax/libs/dat-gui/0.7.6/dat.gui.min.js" integrity="sha256-HJ7j+71YYw6Kcs8THwQV9lXmPOcR0eXlg7n8KRTZsyA=" crossorigin="anonymous"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/106/three.min.js" integrity="sha256-tAVw6WRAXc3td2Esrjd28l54s3P2y7CDFu1271mu5LE=" crossorigin="anonymous"></script>
    		<script src="https://unpkg.com/three@0.85.0/examples/js/libs/stats.min.js"></script>
    		<script src="https://unpkg.com/three@0.85.0/examples/js/controls/OrbitControls.js"></script>
    	</head>
    	<body>
    
    		<div id ="webGL-container">
            </div>
    
    		<script src="GLTFLoader.js" charset="utf-8"></script>
    		<script src="script.js"></script>
    
    	</body>
    </html>


## Load a scene
### Variables

    var scene, camera, renderer;
    var controls, guiControls, datGUI;
    var axis, grid;
    var cubeGeometry, planeGeometry;
    var cubeMaterial, planeMaterial;
    var cube, plane;
    var spotLight, ambientLight;
    var lights;
    var stats;
    var helper;
    var obj, monkey;
    var SCREEN_WIDTH, SCREEN_HEIGHT;

### Init

    function initScene() {
      /*creates empty scene object and renderer*/
      scene = new THREE.Scene(); {
        const color = 0x238189; // white
        // const near = 10;
        // const far = 200;
        scene.fog = new THREE.FogExp2(color, 0.01300);
      }
      camera = new THREE.PerspectiveCamera(45, window.innerWidth / window.innerHeight, .1, 500);
      renderer = new THREE.WebGLRenderer({
        antialias: true
      });
    
      renderer.setClearColor(0x238189);
      renderer.setSize(window.innerWidth, window.innerHeight);
      renderer.shadowMap.enabled = true;
      renderer.shadowMapSoft = true;
      document.querySelector("#webGL-container").append(renderer.domElement);
    
      /*add controls*/
      controls = new THREE.OrbitControls(camera, renderer.domElement);
      controls.addEventListener('change', render);
    
      /*adds helpers*/
      axis = new THREE.AxesHelper(10);
      scene.add(axis);
      grid = new THREE.GridHelper(50, 5);
      scene.add(grid);
    
      //camera
      camera.position.x = 40;
      camera.position.y = 40;
      camera.position.z = 40;
      camera.lookAt(scene.position);
    
      /*stats*/
      stats = new Stats();
      stats.domElement.style.position = 'absolute';
      stats.domElement.style.left = '0px';
      stats.domElement.style.top = '0px';
      document.querySelector("#webGL-container").append(stats.domElement);
    
    }

### Init custom mesh

    async function initCustomMesh() {
    
      var gltfLoader = new THREE.GLTFLoader();
      gltfLoader.load('assets/monkey.glb', (gltf) => {
      monkey = gltf.scene.getObjectByName('Suzanne');
      scene.add(monkey);
      monkey.position.y = 7;
      monkey.material= cubeMaterial;
      monkey.castShadow = true;
      monkey.scale.set(2,2,2);
      console.log(monkey);    
      }, undefined, function(error) {    
        console.error(error);
      });
    }

### Init geometry

    function initGeo() {
    
      /*create cube*/
      cubeGeometry = new THREE.BoxGeometry(5, 5, 5);
      cubeMaterial = new THREE.MeshPhongMaterial({
        color: 0xff674d
      });
      cube = new THREE.Mesh(cubeGeometry, cubeMaterial);
    
    
      cubeGeometry2 = new THREE.BoxGeometry(2, 2, 2);
      cube2 = new THREE.Mesh(cubeGeometry2, cubeMaterial);
      cube.add(cube2);
      cube2.position.x = 4;
      cube2.position.y = 4;
      cube2.position.z = 4;
      cube2.castShadow = true;
    
      cubeGeometry3 = new THREE.BoxGeometry(1, 1, 1);
      cube3 = new THREE.Mesh(cubeGeometry3, cubeMaterial);
      cube.add(cube3);
      cube3.position.x = -4;
      cube3.position.y = -4;
      cube3.position.z = -4;
      cube3.castShadow = true;
    
      /*create plane*/
      planeGeometry = new THREE.PlaneGeometry(100, 100, 100);
      planeMaterial = new THREE.MeshPhongMaterial({
        color: 0xe8f3ee
      });
      plane = new THREE.Mesh(planeGeometry, planeMaterial);
    
      /*position and add objects to scene*/
      cube.position.x = 2.5;
      cube.position.y = 15;
      cube.position.z = 2.5;
      cube.castShadow = true;
      cube.receiveShadow = true;
      scene.add(cube);
    
    
      plane.rotation.x = -.5 * Math.PI;
      plane.receiveShadow = true;
      scene.add(plane);
    
    }


### Init lights

    function initLights() {
      /*adds spot light with starting parameters*/
      spotLight = new THREE.SpotLight(0xffd2b9);
    
      spotLight.position.set(-8, 48, 41);
      spotLight.intensity = 1;
      // no more than Math.PI/2
      spotLight.angle = Math.PI / 3;
      spotLight.distance = 0;
      //spotLight.intensity = guiControls.intensity;
      //spotLight.distance = guiControls.distance;
      //spotLight.angle = guiControls.angle;
      spotLight.castShadow = true;
      spotLight.shadow.camera.fov = 1;
      scene.add(spotLight);
    
      //Set up shadow properties for the light
      spotLight.shadow.mapSize.width = 1024; // default
      spotLight.shadow.mapSize.height = 1024; // default
      spotLight.shadow.camera.near = 20; // default
      spotLight.shadow.camera.far = 80 // default
    
      var spotLightHelper = new THREE.SpotLightHelper(spotLight);
      scene.add(spotLightHelper);
      shadow = new THREE.CameraHelper(spotLight.shadow.camera);
      scene.add(shadow);
    
    
      ambientLight = new THREE.AmbientLight(0x3c61d9);
      scene.add(ambientLight);
    
      var light = new THREE.HemisphereLight(0xff0000, 0x0000ff, 0.8);
      scene.add(light);
    }

### Init GUI

    function initGUI() {
    
      /*datGUI controls object*/
      guiControls = new function() {
    
    
        this.lightX = 20;
        this.lightY = 35;
        this.lightZ = 40;
        this.intensity = 1;
        this.distance = 0;
        this.angle = 1.570;
    
        this.target = cube;
        this.color = 0xff0000;
    
      }
    
      /*adds controls to scene*/
      datGUI = new dat.GUI();
    
      datGUI.add(guiControls, 'lightX', -60, 180);
      datGUI.add(guiControls, 'lightY', 0, 180);
      datGUI.add(guiControls, 'lightZ', -60, 180);
    
    
      datGUI.add(guiControls, 'intensity', 0.01, 5).onChange(function(value) {
        spotLight.intensity = value;
      });
      datGUI.add(guiControls, 'distance', 0, 1000).onChange(function(value) {
        spotLight.distance = value;
      });
      datGUI.add(guiControls, 'angle', 1, 90).onChange(function(value) {
        spotLight.angle = value;
      });
      datGUI.addColor(guiControls, 'color').onChange(function(val) {
        ambientLight.color.setHex(val);
    
      });
      datGUI.close();
    
    }


### Render

    let levitation = 0.03;
    
    function render() {
    
    
      if (monkey) {
          monkey.rotation.y -= 0.02;
      }
    
      cube.rotation.x += 0.01;
      cube.rotation.y += 0.01;
      cube.rotation.z += 0.01;
    
      cube.position.y += levitation;
      if (cube.position.y > 20 || cube.position.y < 10) {
        levitation *= -1;
      }
    
      cube2.rotation.x += 0.02;
      cube3.rotation.x += 0.03;
    
      spotLight.position.x = guiControls.lightX;
      spotLight.position.y = guiControls.lightY;
      spotLight.position.z = guiControls.lightZ;
    }

### Animation

    function animate() {
      requestAnimationFrame(animate);
      render();
      stats.update();
      renderer.render(scene, camera);
    }
### Resize

    window.addEventListener('resize', onResize, false);
    
    function onResize() {
    
      SCREEN_WIDTH = window.innerWidth;
      SCREEN_HEIGHT = window.innerHeight;
    
      camera.aspect = SCREEN_WIDTH / SCREEN_HEIGHT;
      camera.updateProjectionMatrix();
    
      renderer.setSize(SCREEN_WIDTH, SCREEN_HEIGHT);
    }
### launching all the functions

    ///////////////
    //
    //  Launch Function
    //
    ///////////////
    
    initScene();
    initGUI();
    initGeo();
    initLights();
    initCustomMesh();
    animate();

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk1NzIyNjc4MCwtMTQ2MjYxNDkzXX0=
-->