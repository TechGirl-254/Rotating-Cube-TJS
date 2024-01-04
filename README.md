# Basic Three JS Tutorial: A Rotating Cube

## Creating A Scene

In ThreeJS, a scene is the layout that the user sees. To make a TJS scene, you need three things:

- A scene: The scene is the layout of the app. Here's how to create it:
  - const scene = new THREE.Scene()
- A camera: This is the user's view. You can create it using multiple methods, but in this project, we will use the PerspectiveCamera method.
  - const camera = new THREE.PerspectiveCamera(a, b, c, d).

This method takes four arguments as follows:

1. Field of view: The extent of the scene that the user can see.
2. Aspect ratio: The value of the width/height. It determines how images appear when display size changes.
3. Near: Objects in the scene whose value is equal to or less than near are not rendered.
4. Far: Objects in the scene whose value is equal to or greater than near are not rendered.

- Renderer: const renderer = new THREE.WebGLRenderer(). The renerer instance helps us manipulate what gets rendered and how it gets rendered.
  For example, to render a scene, we use the renderer instance and setSize method to determine specifiy the size of the area to be rendered. For a web app, this is typically the size of the browser window. - renderer.setSize(window.innerWidth, window.innerHeight);

We also need to add the renderer to the index.html as follows:

- document.body.appendChild(renderer.domElement);

## Adding Content to The Scene

With the scene ready, we need to add the content that will be animated.

You can create animated content using multiple functions, but for our case, we will use the ones below.

- BoxGeometry: Creates cubes and cuboids
- MeshBasicMaterial: Takes an object of properties like color. It gives the content its texture.
- Mesh: Takes the geometry created and fuses it to the material.

## Rendering The Scene

To render a scene, we need an animate/render loop. This renders the content everytime the screen refreshes.

Everything in the scene must be rendered using the animate loop. Here's the animating function.

- function animate() {
  requestAnimationFrame(animate);
  cube.rotation.x += 0.04;
  cube.rotation.y += 0.04;
  renderer.render(scene, camera);
  }
  animate();
