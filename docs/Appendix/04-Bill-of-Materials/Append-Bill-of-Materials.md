# Selection and Rationale

## Vision System

| Solution | Pros | Cons | Price |
|---|---|---|---:|
|![REALTEK AMB82 MINI IOT AI CAMERA](../assets/Realtek_AMB82.png)<br>**REALTEK AMB82 MINI IOT AI CAMERA** | - On-board AI object detection software<br>- Wide-angle lens allows for full vision of pipe ahead<br>- High-resolution camera with fast frame rates allows for quick real-time object detection | - Focal length is non-adjustable and set for long distance<br>- Short custom data cable means the entire module will need a unique mounting solution | $30 |
|![OV5640 CAMERA](../assets/OV5640.png)<br>**OV5640 CAMERA XIAO ESP32S3 SENSE**| - Familiarity with platform allows for more focus on object detection development time<br>- Long data cable allows for better mounting solution<br>- High resolution with fast frame rates<br>- Minimum focal length is about 10 cm, allowing for better inspection of small pipes<br>- Low cost<br>- Uses ESP32-S3 chip for on-board object detection | - Less RAM than other options | $24 |
|![m5stack](../assets/m5stack.png)<br>**M5Stack** | - Highest processing power of any option<br>- High resolution and high frame-rate video<br>- On-board object-detection models preconfigured for common applications | - Bulky<br>- Way out of budget<br>- High power cost | $95 |

### Choice

**OV5640 CAMERA XIAO ESP32S3 SENSE** — upgrade to previously used module

### Rationale

The camera provides excellent video resolution and frame rate at a very low cost compared to the other options. It is also familiar to our team, so it will cut down on the amount of time needed to write the necessary software.

---

## Drive System

| Solution | Pros | Cons | Price |
|---|---|---|---:|
| ![NFP-GM25](../assets/NFP-GM25.png)<br>**NFP-GM25-310-OEN** | - True optical encoder<br>- Stronger than N20<br>- 360 CPR provides good feedback<br>- 3.3/5 V encoder interface<br>- Multiple gear ratios<br>- Compact enough for the pipe robot<br>- Good balance of speed and torque | - Larger than N20<br>- Heavier than N20<br>- 4 mm shaft<br>- 7.4 V rather than 5 V<br>- More expensive than basic N20 motors | $15 |
| ![Planetary Gear Motor](../assets/PlanetaryGearMotor.png)<br>**Planetary Gear Motor with Optical Encoder** | - Very high torque<br>- Planetary gearbox<br>- Optical encoder<br>- Available in 6 V<br>- Excellent for heavier robots<br>- Strong gearbox<br>- Good positional accuracy | - 36 mm diameter<br>- Much heavier<br>- Could be difficult to fit inside a 4-inch pipe<br>- Higher current requirements<br>- More expensive | $20 |
| ![GM37-520](../assets/GM37-520.png)<br>**GM37-520** | - High torque<br>- Metal gearbox<br>- Optical encoder versions available<br>- Many gear ratios<br>- Good for heavier robots<br>- Stronger shaft and gearbox | - 37 mm diameter<br>- Large for a 4-inch pipe<br>- Heavy<br>- Typically 12 V<br>- Higher power consumption<br>- More motor than the robot probably needs | $40 |
| ![Rob-28633](../assets/ROB-28633.png)<br>**ROB-28633** | - Compact and lightweight<br>- Built-in Hall-effect encoder<br>- 882 counts/revolution<br>- Good speed and torque for its size<br>- 31.5:1 gear ratio<br>- Good for ESP32 control<br>- Fits well in a 4–6 inch pipe | - Encoder is magnetic, not optical<br>- Limited torque compared with larger motors<br>- Wheel slip can affect distance accuracy<br>- Small gearbox can be damaged if stalled<br>- Requires a motor driver | $9.90 |

### Choice

**SparkFun ROB-28633 N20 Motor With Encoder**

### Rationale

The ROB-28633 was selected because its compact N20 form factor makes it well suited for the 4–6 inch pipe inspection robot. The integrated Hall-effect encoder provides 882 counts per revolution for accurate motor speed and distance feedback. Its 31.5:1 gear ratio provides a good balance between speed and torque, while its small size and low weight help keep the robot compact and maneuverable. The motor is also compatible with the ESP32 control system and is available as a matched pair for the two-wheel drive system.

---

## Drive Sensing

| Solution | Pros | Cons | Price |
|---|---|---|---:|
| ![MicoAir MTF-02P](../assets/MTF-02P.png)<br>**MicoAir MTF-02P** | - Optical flow + range in one<br>- 6 m range<br>- Very small and lightweight<br>- 5 V operation<br>- 50 Hz output<br>- UART communication | - More expensive than basic optical-flow sensors<br>- Requires UART programming<br>- Optical flow requires adequate lighting | $28 |
| ![Holybro PMW3901](../assets/PMW3901.png)<br>**Holybro PMW3901** | - Small and lightweight<br>- Good optical-flow tracking<br>- 95 Hz output<br>- UART interface<br>- Low power consumption<br>- Easy to integrate | - No built-in distance sensor<br>- Requires a separate range sensor<br>- Less functionality than the MTF-02P | $20.59 |
| ![Holybro H-Flow](../assets/H-Flow.png)<br>**Holybro H-Flow** | - Optical flow + distance sensor<br>- Up to 30 m range<br>- Built-in 6-axis IMU<br>- Works in low-light conditions<br>- CAN/DroneCAN communication<br>- Very capable sensor | - Much more expensive<br>- Heavier at 15.2 g<br>- More complicated than needed<br>- Larger than the MTF-02P | $145 |

### Choice

**MicoAir Optical Flow & Range Sensor MTF-02P**

### Rationale

The MTF-02P was selected because it combines optical flow and distance measurement into one compact and lightweight sensor. Its 6 m range, 50 Hz output, and 5 V operation make it well suited for the pipe inspection robot. Using one sensor for both functions reduces the number of components and saves space, while providing movement and distance data that can work with the N20 motor encoders to improve the robot’s navigation and return-to-start accuracy.

---

## Chassis

| Solution | Pros | Cons | Price |
|---|---|---|---:|
| ![Mini RC Truck](../assets/GreenMonster.png)<br>**Mini RC Truck, 1:64 Scale Monster Truck** | - Fits within 4-inch pipe with its cosmetics attached<br>- Allows room to attach components with cosmetic shell removed<br>- Trailer hitch can be used to attach rescue line without modification<br>- Off-road tires allow for easy traversal of pipes | - Uses generic remote with limited range (30 m)<br>- Limited battery life (20 minutes)<br>- High price means only one can be bought for prototyping | $18 each |
| ![Mini CyberTruck](../assets/CyberStuck.png)<br>**Mini RC Truck, 1:64 Scale Monster Truck Remote Control Car with Lights** | - Allows more room to attach components with cosmetic shell removed<br>- Trailer hitch can be used to attach rescue line without modification<br>- Off-road tires allow for easy traversal of pipes<br>- Can use phone app instead of remote | - Taller than needed (4.1 inches)<br>- Uses generic remote with limited range (30 m)<br>- Limited battery life (20 minutes)<br>- High price means only one can be bought for prototyping<br>- Phone app has very limited range | $19 each |
| ![Mini Tank](../assets/GrayTank.png)<br>**2.4GHz Mini RC Tank Toy with LED and Rotating Turret** | - Flat chassis allows for stable platform to build from<br>- Rotating turret could be utilized to give a 360° camera view<br>- Treads allow for easier traversal of rough terrain | - High price point makes any testing or modification risky because duplicates cannot be afforded<br>- Turret mechanism is difficult to disassemble carefully<br>- Paying for unneeded features such as speakers | $23 each |

### Choice

**2.4 GHz Mini RC Tank Chassis**

### Rationale

The tank chassis was selected because its treads provide better traction and reduce slipping compared to wheeled chassis. The flat chassis provides a stable platform for mounting the ESP32, motor driver, sensors, and battery, while the compact design allows the robot to traverse rough and uneven surfaces inside the pipe.

---

## Motor Controller

| Solution | Pros | Cons | Price |
|---|---|---|---:|
| ![DRV8833PWPR](../assets/DRV8833.png)<br>**DRV8833PWPR** | - Surface-mount HTSSOP package<br>- Controls 2 DC motors<br>- 1.5 A output per channel<br>- Compact and lightweight<br>- Works directly with ESP32 PWM signals<br>- Low cost | - Motor supply limited to 10.8 V<br>- Less current capability than DRV8848 | $3.02 |
| ![TB6612FNG](../assets/TB6612.png)<br>**TB6612FNG** | - Surface-mount 24-SSOP package<br>- Controls 2 DC motors<br>- Up to 1 A continuous per channel<br>- Motor voltage up to 13.5 V<br>- Low power consumption<br>- Inexpensive | - Larger package than DRV8833<br>- Lower current capability<br>- Operating temperature is only -20°C to 85°C | $2.04 |
| ![DRV8848PWPR](../assets/DRV8848.png)<br>**DRV8848PWPR** | - Surface-mount HTSSOP package<br>- Controls 2 DC motors<br>- Up to 2 A per bridge / 4 A parallel<br>- Motor voltage 4–18 V<br>- More current capacity and voltage headroom<br>- Built-in protection features | - More capability than the small N20 motors require<br>- Slightly more expensive<br>- More complex than necessary for this project | $2.97 |

### Choice

**DRV8833PWPR Motor Driver**

### Rationale

The DRV8833PWPR was selected because it can operate with a 5 V motor supply, supports two DC motors, and can be soldered directly to the PCB using its surface-mount package. Its compact size, low cost, and compatibility with the ESP32 make it well suited for controlling the two N20 motors while keeping the robot’s electronics compact.
