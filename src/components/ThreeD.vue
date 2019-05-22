<template>
    <div class="three-dee">
        <h4> {{ text }}</h4>
        <div id="three-canvas" @touchdown="this.rotate = 0;">

        </div>
        <p>Rotate with your finger</p>

    </div>
</template>

<script>
import * as Three from 'three';
import {OrbitControls} from "three/examples/jsm/controls/OrbitControls";
import {GLTFLoader} from "three/examples/jsm/loaders/GLTFLoader";

    export default {
        name: 'ThreeD',
        props: ['text'],
        data: function() {
            return {
                hasRendered: false,
                scene: null,
                model: null,
            }
        },
        created(){
            window.addEventListener('rezise', this.onWindowResize, false);
        },
        mounted() {
            this.init();
            //this.animate();
        },
        methods: {
            init: function() {
                let container = document.getElementById('three-canvas');
                //let model;

                this.camera = new Three.PerspectiveCamera(70, container.clientWidth/container.clientHeight, 0.01, 10);
                this.controls = new OrbitControls( this.camera );

                this.camera.position.z = 1;

                this.controls.update();
                this.controls.enableZoom = false;
                this.controls.rotateSpeed = 0.2;
                this.controls.enableDamping = true;
                this.controls.dampingFactor = 0.05;
                this.controls.autoRotate = true;
                this.controls.autoRotateSpeed = 0.2;

                this.scene = new Three.Scene();

                this.ambientLight = new Three.HemisphereLight( 0xddeeff, 0x0f0e0d, 5 );

                this.mainLight = new Three.DirectionalLight( 0xffffff, 2 );
                this.mainLight.position.set( 10, 10, 10 );

                this.scene.add( this.ambientLight, this.mainLight );

                let geometry = new Three.BoxGeometry(0.1, 0.1, 0.1);
                let material = new Three.MeshNormalMaterial();

                this.mesh = new Three.Mesh(geometry, material);
                this.scene.add(this.mesh);

                this.renderer = new Three.WebGLRenderer({
                        antialias: true,
                        alpha: true
                    });
                this.renderer.setSize(container.clientWidth, container.clientHeight);
                
                container.appendChild(this.renderer.domElement);
                this.loadModel()

            },
            animate: function() {
                requestAnimationFrame(this.animate);
                //this.model.rotation.y += this.rotate;
                //this.mesh.rotation.y += 0.02;
                this.controls.update();
                this.renderer.render(this.scene, this.camera);
            },
            onWindowResize: function(event) {
                this.camera.aspect = window.innerWidth / window.innerHeight;
                this.camera.updateProjectionMatrix();

                this.renderer.setSize( window.innerWidth, window.innerHeight );
            },
            loadModel: function(){
                this.loader = new GLTFLoader();
                this.loader.load(
                    './models/SM_Skyscraper_02.gltf',
                    (gltf) => {
                        this.model = gltf.scene;
                        this.model.traverse( function(child){
                            if(child.isMesh){
                                child.recieveShadow = true;
                            }
                        });
                        let modelSize = 0.003;
                        this.model.scale.x = modelSize;
                        this.model.scale.y = modelSize;
                        this.model.scale.z = modelSize;
                        this.model.position.set(0, -0.5, 0);
                        this.scene.add(this.model);
                        this.animate();
                    }, undefined, function(error){
                        console.log(error);
                    }
                );
            }
        },
    }
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';
#three-canvas {
    height: 335px;
    width: 100%;
    margin-top: 24px;
    touch-action: none;
}

p {
    text-align: center;
    margin-bottom: 0;
}

h4 {
    margin-top: 0;
    -webkit-text-fill-color: transparent;
    -webkit-text-stroke: .03em $primaryColor;
}

</style>