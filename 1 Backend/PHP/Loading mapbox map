# Loading a map 

    <?php
    	$map_id = uniqid();
    	$locations = $locations ? $locations : array();
    ?>
    
    <div class="map map-<?php echo $map_id; ?>" id="location"></div>
    <script>
    	(function() {
    		const map = document.querySelector('.map-<?php echo $map_id; ?>');
    		map.locations = <?php echo json_encode($locations); ?>;
    	})();
    </script>
    
    
    <?php $map_id = $locations = Null; ?>
    
    
    ____________________
    
    
    .map {
    	width: 100%;
    	height: 70vh;
    }
    
    .marker {
    	position: absolute;
    	font-size: 65px;
    	color: $quaternary;
    	text-shadow: 1px 1px 5px rgba(0, 0, 0, .2);
    	cursor: pointer;
    }
    
    .mapboxgl-popup-content {
    	p {
    		margin: 0;
    	}
    }
    
    .mapboxgl-ctrl-group {
    	& > button {
    		border-radius: 0;
    	}
    }
    
    
    ----------------------
    
    
    (() => {
    
    	class Map {
    		constructor(selector) {
    			this.root = typeof selector === 'object' ? selector : document.querySelector(selector);
    			this.locations = this.root.locations;
    			this.map;
    			this.markers = [];
    			this.popups = [];
    			this.bounds = new mapboxgl.LngLatBounds();
    			this.init();
    		}
    
    		init() {
    			this.map = new mapboxgl.Map({
    			  container: this.root,
    			  style: 'mapbox://styles/duotones/cjwjbgbh2056h1cr2xg4mvp5y',
    			  center: [7.248760, 47.143299],
    				scrollZoom: false,
    			  zoom: 10
    			});
    
    			this.map.addControl(new mapboxgl.NavigationControl(), 'top-left');
    
    			this.addMarkers();
    			this.map.fitBounds(this.bounds, {
    				maxZoom: 13.9,
    				padding: 150,
    				duration: 0
    			});
    			this.markers[0].togglePopup();
    		}
    
    		addMarkers() {
    			this.locations.forEach((loc) => {
    				const el = document.createElement('i');
    				el.innerHTML = 'location_fill';
    				el.className = 'marker noetzel-icons';
    
    				const popup = new mapboxgl.Popup({
    					offset: 65,
    					closeButton: false,
    				}).setHTML(loc['text'])
    
    				const marker = new mapboxgl.Marker({
    					element: el,
    					anchor: 'bottom'
    				}).setLngLat([loc['lng'], loc['lat']]).setPopup(popup).addTo(this.map);
    
    				this.markers.push(marker);
    				this.bounds.extend( new mapboxgl.LngLat( loc['lng'], loc['lat'] ) );
    			});
    		}
    	}
    
    	mapboxgl.accessToken = 'pk.eyJ1IjoiZHVvdG9uZXMiLCJhIjoiY2p3amI3MWRiMDk4YjQzbnMxanhmMzE0cyJ9.2JfVO8MnUl6ek1Me98nP4Q';
    
    	const mapElements = document.querySelectorAll('.map');
    	mapElements.forEach((el) => {
    		new Map(el);
    	})
    
    })();

<!--stackedit_data:
eyJoaXN0b3J5IjpbNDAxNzQxMjIsLTE3MjM1MzYxOTBdfQ==
-->