# HydroGrasp

This is the official open-source repository for the paper:

**HydroGrasp: A Hydraulic Multi-Fingered Gripper**

📄 [Read the Paper](https://doi.org/10.1109/robio66223.2025.11377340)

---

## Hardware

### Manipulator

To manufacture a manipulator, you need to 3D print the following models in `CAD/Manipulator`. It is recommend to use resin (SLA) 3D printing to achieve better structural accuracy.

#### 3D Printing BOM

| Item | Quantity | Recommand Process|
|------|----------|------------------|
|Base|1|SLA|
|EndNut|6|SLA / FDM|
|Link0|3|SLA|
|Link1|3|SLA|
|Link2|3|SLA|
|Sleeve1|3|SLA|
|Sleeve2|3|SLA|

To assemble these parts, you will also need the following components:

#### Component BOM

| Item | Specification | Quantity | Notes | Link |
|------|---------------|----------|-------|------|
| Dynamixel Servos | XL-330-M288-T | 3 | with cables & screws | https://en.robotis.com/shop_en/item.php?it_id=902-0163-000 |
| Shoulder Bolt | 4 × 22 × M3 | 3 | - | - |
| Shoulder Bolt | 4 × 35 × M3 | 12 | - | - |
| Lock Nut | M3 anti-slip | 15 | - | - |
| Heat-set Insert | M3 × 5 mm (height) × 3.5 mm (OD) | 6 | - | - |
| Push Rod | CJ1B4-15SU4 | 3 | - | https://e.tb.cn/h.iitMhi8EHR5U38x?tk=sMsP5Y1MS0p |
| Push Rod | CJ1B4-20SU4 | 3 | - | https://e.tb.cn/h.iitMhi8EHR5U38x?tk=sMsP5Y1MS0p |

### Assembly Instructions

1. Use a soldering iron to embed heat-set inserts into the EndNut.

2. For each of the CJ1B4-15SU4 push rod, remove the black nut at the front end. Pass the threaded portion that originally held the nut through Sleeve2, then reattach and tighten the black nut to secure it.

3. For each of the CJ1B4-20SU4 push rod, remove the black nut at the front end. Pass the threaded portion that originally held the nut through Sleeve1, then reattach and tighten the black nut to secure it.

4. Connect the threaded end of the push rod to the heat-set nut embedded in the EndNut.

5. Referring to the figures in the paper, use 4 × 35 shoulder bolts and lock nuts to connect three finger links and push rods, and adjust the screw tightness so that each joint rotates freely without resistance. Do not install the 4 × 22 screws at this stage.

6. Repeat the above steps three times to assemble three fingers.

7. Use the longer screws from the servo kit to secure the three servos to the base.

8. Attach Link0 of each finger to the servo horns using the longer screws provided in the Dynamixel kit.

9. Referring to the paper’s figures, install the shorter 4 × 22 shoulder bolts.

10. This base can be mounted, as needed, onto the end of xArm, Franka, or UR5. 

### Actuator

#### BOM

| Item | Specification | Quantity | Notes | Link |
|------|---------------|----------|-------|------|
| 3D Printed Parts | See `CAD/Actuator` | 1 set | Print each file once | - |
| Dynamixel Servos | XL-330-M288-T | 1 | with cables & screws | https://en.robotis.com/shop_en/item.php?it_id=902-0163-000 |
| syringe | 1mL | 1 | without needle | - |

### Assembly Instructions

1. Attach the gear to the servo horns using the longer screws provided in the Dynamixel kit.

2. Use the longer screws from the servo kit to secure the servo to the base.

3. Slide the rack into the groove of the base.

4. Insert the syringe plunger and handle into the grooves of the rack and the base, respectively.

### System Assembly

To build the complete system, you will need at least one manipulator and six actuators. In addition, the following materials are required

| Item | Specification | Quantity | Notes |
|------|---------------|----------|-------|
| PVC tube | 4mm*2.5mm | as needed | - |
| T-type connectors | Suit for 4 mm tubing diameter | as needed | optional |

To drive each degree of freedom, connect PVC tube between the end of the pneumatic actuator and the front end of the syringe. Then fill the closed cavity formed by the syringe, tubing, and actuator with purified water, ensuring that all air is removed. When the actuator is in the retracted state, the syringe plunger should be fully extended to achieve the maximum stroke.

In addition, you can use a T-type connector to assign two actuators to a single pneumatic rod, enabling hybrid control.

Finally, to drive the Dynamixel servos, you will need the following materials. Please refer to the [official manual](https://emanual.robotis.com/docs/en/dxl/x/xl330-m288/) for proper connection and control of the servos.

| Item | Specification | Quantity | Link |
|------|---------------|----------|------|
| U2D2 Hub | - | 1 | https://en.robotis.com/shop_en/item.php?it_id=902-0132-000 |
| U2D2 PHB Set | - | 1 | https://en.robotis.com/shop_en/item.php?it_id=902-0145-001 |
| DC Power Supply | 5V | 1 | - |

---

## Software

### Installation

The Dynamixel SDK can be installed using the following command:

```bash
pip install dynamixel_sdk
```

### Usage

Please refer to the [Official Dynamixel SDK Documentation](https://emanual.robotis.com/docs/en/software/dynamixel/dynamixel_sdk/download/) and our [paper](https://doi.org/10.1109/robio66223.2025.11377340) to implement the servo communication and actuation logic.

---

## Citation

If you use this repository in your research, please cite:

```bash
@INPROCEEDINGS{Zhang2025HydroGrasp,
  author={Zhang, Peiran and Tang, Ziyuan and Hu, Runze and Xiao, Chenxi},
  booktitle={2025 IEEE International Conference on Robotics and Biomimetics (ROBIO)}, 
  title={HydroGrasp: A Hydraulic Multi-Fingered Gripper}, 
  year={2025},
  volume={},
  number={},
  pages={442-447},
  doi={10.1109/ROBIO66223.2025.11377340}}
```
