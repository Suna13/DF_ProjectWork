# DFE\_09 - Digital Factory Project Work

## How to run (replication)

Open the final model directly in VEB.js (scene, environment, animation and 3D models are served from this repository via GitHub Pages):

https://digital-factory.io/vebjs/?inputscene=https://suna13.github.io/DF\_Projectwork/DFE\_09\_V10\&inputenv=https://suna13.github.io/DF\_Projectwork/env/DFE\_09\_env\&inputanim=https://suna13.github.io/DF\_Projectwork/anim/DFE\_09\_anim\&repoMod3d=https://suna13.github.io/DF\_Projectwork/assets/

The simulation starts automatically and ends with all ten parts in the box (about 4 min 32 s). The validation scenes in `test/` (e.g. `test/DFE\_09\_WSA`, `test/DFE\_09\_WSB`) are opened with the same link, replacing `DFE\_09\_V10` in `inputscene`; in these scenes each step is triggered manually with the `next`/`back` events.

## Package content

**Final model**

* `DFE\_09\_V10.json`: final scene (assets, layout and StateCharts of B1, Sensor1, WSA, AGV, AGV.surface and WSB).
* `env/DFE\_09\_env.json`: environment (cameras, lights, physics).
* `anim/DFE\_09\_anim.json`: animation, starts the conveyor (`B1startF`) after 1 s.

**3D models (`assets/`)**

* Used by the final scene: `UR.glb` and `UR\_Mag.glb` (UR robots WSA and WSB, the latter with the magnetic gripper), `AGV\_V3.glb` (AGV with lowered crossbars), `Sensor.glb`, `Sensor2.glb`, `ConveyorNew.glb`, `Part.glb`, `Box\_large.glb`, `Grid.glb`.
* Source models: `UR\_Pick\_and\_Place\_Station.glb` (base of UR.glb and UR\_Mag.glb), `AGV\_original.glb` and `AGV.glb` (third-party AGV, converted and scaled; base of AGV\_V3.glb).
* Helper models, not loaded by the final scene: `AGV\_full.glb` and `Box\_full.glb`, with the ten parts placed in the planned layout on the AGV and in the box, used to read the target positions of the parts.

**Validation (`test/`)**

* `DFE\_09\_WSA.json`: loading cycle of WSA, executed step by step with the `WSAnext`/`WSAback` events.
* `DFE\_09\_WSB.json`: unloading cycle of WSB with the AGV already in its final position and the parts in their final positions on it, executed step by step with the `WSBnext`/`WSBback` events.
* `DFE\_09\_AGV.json`, `DFE\_09\_AGV\_fast1.json`, `DFE\_09\_AGV\_fast2.json`: AGV travel at 100 mm/s (original AGV), 255 mm/s and 200 mm/s (AGV\_V3); each segment is started manually with the `AGVgo` event. At 255 mm/s the parts fall from the AGV, at 200 mm/s (final value) they are transported correctly.
* `DFE\_09\_V10.json`: scene exported from VEB.js with the AGV at the end of its path, used to read the final positions of the parts on the AGV.
* `Excel.xlsx`: conversion of the joint rotations read in VEB.js (0-360 deg) into the values used in the StateCharts (correction of -360 deg above 180 deg, conversion to radians) and computation of the AGV durations from distance and speed.

**Documentation**

* `Report\_extended.docx`: technical report.
* `README.md`: package content and replication instructions.

## Modelli 3D di terze parti

**Industrial - 3D AGV \& Trolley - Omrom** di [Cels](https://sketchfab.com/nguyenngockhanh.nnk)

Fonte: https://sketchfab.com/3d-models/industrial-3d-agv-trolley-omrom-9f5e1d24a7654c3d85394a5b5a9594e4

Licenza: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

Modifiche: convertito in GLB e scalato per l'uso in veb.js.

File: `assets/<AGV>.glb`

