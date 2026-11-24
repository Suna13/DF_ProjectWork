# DFE_09 - Digital Factory Project Work

## How to run

Open the final model directly in VEB.js (scene, environment, animation and 3D models are served from this repository via GitHub Pages):

https://digital-factory.io/vebjs/?inputscene=https://suna13.github.io/DF_ProjectWork/DFE_09_V10&inputenv=https://suna13.github.io/DF_ProjectWork/env/DFE_09_env&inputanim=https://suna13.github.io/DF_ProjectWork/anim/DFE_09_anim&repoMod3d=https://suna13.github.io/DF_ProjectWork/assets/

The simulation starts automatically and ends with all ten parts in the box (about 4 min 32 s). The test scenes in `test/` (e.g. `test/DFE_09_WSA`, `test/DFE_09_WSB`) are opened with the same link, replacing `DFE_09_V10` in `inputscene`; in these scenes each step is triggered manually with the `next`/`back` events.

## Package content

**Final model**

* `DFE_09_V10.json`: final scene.
* `env/DFE_09_env.json`: environment.
* `anim/DFE_09_anim.json`: animation.

**3D models (`assets/`)**

* Used by the final scene: `UR.glb` and `UR_Mag.glb` (UR robots WSA and WSB, the latter with the magnetic gripper), `AGV_V3.glb` (AGV with lowered crossbars), `Sensor.glb`, `Sensor2.glb`, `ConveyorNew.glb`, `Part.glb`, `Box_large.glb`, `Grid.glb`.
* Source models: `UR_Pick_and_Place_Station.glb` (base of UR.glb and UR_Mag.glb), `AGV_original.glb` and `AGV.glb` (third-party AGV, converted and scaled; base of AGV_V3.glb).
* Helper models, not loaded by the final scene: `AGV_full.glb` and `Box_full.glb`, with the ten parts placed in the planned layout on the AGV and in the box, used to read the target positions of the parts.

**Validation (`test/`)**

* `DFE_09_WSA.json`: loading cycle of WSA, executed step by step with the `WSAnext`/`WSAback` events.
* `DFE_09_WSB.json`: unloading cycle of WSB with the AGV already in its final position and the parts in their final positions on it, executed step by step with the `WSBnext`/`WSBback` events.
* `DFE_09_AGV.json`, `DFE_09_AGV_fast1.json`, `DFE_09_AGV_fast2.json`: AGV travel at 100 mm/s (original AGV), 255 mm/s and 200 mm/s (AGV_V3); each segment is started manually with the `AGVgo` event. At 255 mm/s the parts fall from the AGV, at 200 mm/s (final value) they are transported correctly.
* `DFE_09_V10.json`: scene exported from VEB.js with the AGV at the end of its path, used to read the final positions of the parts on the AGV.
* `Excel.xlsx`: conversion of the joint rotations read in VEB.js (0-360 deg) into the values used in the StateCharts (correction of -360 deg above 180 deg, conversion to radians) and computation of the AGV durations from distance and speed.

**Documentation**

* `Report_extended.docx`: technical report.
* `README.md`: package content and replication instructions.
* `DFE_09.xlsm`: original assignment spreadsheet not uploaded. The model was developed directly in the JSON scene file.

## Third-party 3D models

**Industrial - 3D AGV & Trolley - Omrom** by [Cels](https://sketchfab.com/nguyenngockhanh.nnk)

Source: https://sketchfab.com/3d-models/industrial-3d-agv-trolley-omrom-9f5e1d24a7654c3d85394a5b5a9594e4

License: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

Changes: converted to GLB and scaled for use in VEB.js (`assets/AGV.glb`); simplified and modified in Blender, with the front and rear crossbars lowered just above the loading surface (`assets/AGV_V3.glb`, used in the final scene).

Files: `assets/AGV.glb`, `assets/AGV_V3.glb`

