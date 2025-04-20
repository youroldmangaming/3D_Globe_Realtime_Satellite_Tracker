# ISS & Starlink Tracker

A web-based 3D visualization of the International Space Station (ISS) and Starlink satellite constellation orbiting the Earth.

## Description

This project is a interactive 3D simulation built using HTML, CSS, and JavaScript with the Three.js library. It displays a textured 3D model of the Earth, along with the International Space Station (ISS) and markers representing Starlink satellites in their approximate orbits. Users can control the camera, adjust simulation parameters via a graphical user interface (GUI), and track the ISS position.

## Features

* Interactive 3D Earth model with day/night cycle and clouds.

* Visualization of the Moon's orbit.

* Tracking and visualization of the International Space Station (ISS) position.

* Visualization of Starlink satellites (based on fetched data).

* Adjustable simulation speed, Earth rotation, lighting, and atmospheric effects via a GUI.

* Option to follow the ISS with the camera.

* Basic starfield background.

## Setup

To run this project locally, you will need a web server (like Apache, Nginx, or a simple Python HTTP server) to serve the files, as browsers restrict loading local files directly due to security reasons (especially for textures and models).

1. **Save the Code:** Save the provided HTML code as `index.html`.

2. **Three.js Library:** Download the Three.js library. You will need at least the core `three.module.js` file and the `jsm` folder containing addons like `GLTFLoader.js`, `OrbitControls.js`, and `lil-gui.module.min.js`. Place these files in the same directory or a structure that matches the `importmap` and script paths in the HTML (`./three.module.js`, `./jsm/`).

3. **Assets:** You need to provide the texture images and the ISS GLTF model. Create a folder named `textures` in the same directory as `index.html`, and inside `textures`, create a folder named `planets`. Place the following texture files inside `textures/planets/`:

   * `earth_day_4096.jpg` (Day texture)

   * `earth_night_4096.jpg` (Night texture)

   * `earth_bump_roughness_clouds_4096.jpg` (Bump/Roughness/Cloud Alpha texture)

   * `8k_earth_clouds.jpg` (Cloud color texture)

   * `moon_1024.jpg` (Moon texture)
     Also, place your ISS GLTF model file (e.g., `ISS_stationary.glb`) in a location accessible by the `GLTFLoader` (the code currently looks for `./models/ISS_stationary.glb`, so create a `models` folder and place the file there).

4. **Run a Local Server:** Open your terminal or command prompt, navigate to the project directory, and start a local web server.

   * **Python:** `python -m http.server`

   * **Node.js:** If you have Node.js installed, you can use `npx http-server` (install with `npm install -g http-server` if needed).

5. **Open in Browser:** Open your web browser and navigate to the address provided by your local server (usually `http://localhost:8000`).

## Usage

* **Camera Controls:** Use your mouse to orbit, pan, and zoom around the Earth.

* **GUI:** Use the graphical interface (usually in the top-right corner) to adjust various simulation parameters like time scale, rotation speeds, lighting, atmosphere effects, and Starlink visibility.

* **ISS Tracking:** The application attempts to fetch the real-time position of the ISS. You can toggle tracking and camera following using the GUI controls.

## Data Sources

* **ISS Position:** The code is set up to fetch ISS position data, likely from a public API (e.g., `http://api.open-notify.org/iss-now.json`).

* **Starlink Data:** The code includes functionality to fetch Starlink data. Public sources for satellite orbital data like Two-Line Element Sets (TLEs) can be obtained from resources such as [CelesTrak](https://celestrak.org/).

## Potential Improvements

* Implement more accurate Starlink positioning using TLE data and a propagation library.

* Add more detailed 3D models for satellites.

* Include trajectories or trails for the ISS and Starlink satellites.

* Add more celestial bodies or space objects.

* Improve the UI/UX.

* Implement better error handling for data fetching.

## License

(You can add a license here, e.g., MIT, Apache 2.0, etc.)

## Acknowledgements

* Three.js library

* Data providers (e.g., OpenNotify for ISS, CelesTrak for Starlink data)

* Texture and Model creators
