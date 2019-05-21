<template>
    <div class="three-dee">
        <h4> {{ text }}</h4>
        <div id="three-canvas">

        </div>
        <p>Rotate with your finger</p>

    </div>
</template>

<script>
import * as Three from 'three';
import {OrbitControls} from "three/examples/jsm/controls/OrbitControls";

    export default {
        name: 'ThreeD',
        props: ['text'],
        data: function() {
            return {
                hasRendered: false
            }
        },
        methods: {
            init: function() {
                let container = document.getElementById('three-canvas');

                this.camera = new Three.PerspectiveCamera(70, container.clientWidth/container.clientHeight, 0.01, 10);
                this.controls = new OrbitControls( this.camera );

                this.camera.position.z = 1;
                this.controls.update();

                this.scene = new Three.Scene();

                let geometry = new Three.BoxGeometry(0.2, 0.2, 0.2);
                let material = new Three.MeshNormalMaterial();

                this.mesh = new Three.Mesh(geometry, material);
                this.scene.add(this.mesh);

                this.renderer = new Three.WebGLRenderer({
                        antialias: true,
                        alpha: true
                    });
                this.renderer.setSize(container.clientWidth, container.clientHeight);
                
                container.appendChild(this.renderer.domElement);

            },
            animate: function() {
                requestAnimationFrame(this.animate);
                //this.mesh.rotation.x += 0.01;
                //this.mesh.rotation.y += 0.02;
                this.controls.update();
                this.renderer.render(this.scene, this.camera);
            }
        },
        mounted() {
            this.init();
            this.animate();
        }
        /* created(){
            window.addEventListener('resize', this.onWindowResize, false);

            this.scene = new THREE.Scene();
            this.camera = new THREE.PerspectiveCamera( 40, window.innerWidth / window.innerHeight, 0.1, 1000 );
            this.camera.position.z = 40;
            this.camera.position.x = 0;

            this.renderer = new THREE.WebGLRenderer({
                antialias: true
            });
            this.renderer.setClearColor(0xffffff);
            this.renderer.setSize(window.innerWidth - 200, window.innerHeight);

            //this.scene.fog = new THREE.Fog(0x0000ff, 10, 100);
            //console.log(this.renderer);
        },

        mounted(){
            let geometry = new THREE.BoxGeometry(0.2, 0.2, 0.2);
            let material = new THREE.MeshNormalMaterial();

            this.mesh = new THREE.Mesh(geometry, material);
            this.scene.add(this.mesh);

            this.mesh.rotation.x = Math.PI/2;
            this.mesh.position.x = 0;
            this.mesh.position.y = -10;
            this.mesh.position.z = -(this.mesh.geometry.parameters.height/2 -10);

            this.pointLight = new THREE.PointLight({
                color: 0xffffff,
                intensity: 1
            });
            this.pointLight.castShadow = true;
            this.pointLight.position.y = 5;
            this.pointLight.position.z = 20;
            this.scene.add(this.pointLight);

            this.animate = () => {
                this.mesh.rotate();
                this.renderer.render(this.scene, this.camera);
                requestAnimationFrame(this.animate);
            }

            this.render = () => {
                this.$el.appendChild(this.renderer.domElement);
                this.renderer.render(this.scene, this.camera);
                requestAnimationFrame(this.animate);
            }
            if(!this.hasRendered){
                this.render();
            }

        },

        methods: {
            onWindowResize(event) {
                this.camera.aspect = window.innerWidth / window.innerHeight;
                this.camera.updateProjectionMatrix();

                this.renderer.setSize( window.innerWidth, window.innerHeight );
		    }
        }, */
    }
</script>

<style lang="scss" scoped>
#three-canvas {
    height: 335px;
    width: 100%;
    margin-top: 24px;
    touch-action: none;
}

p {
    text-align: center;
}

h4 {
    margin: 0;
}

</style>