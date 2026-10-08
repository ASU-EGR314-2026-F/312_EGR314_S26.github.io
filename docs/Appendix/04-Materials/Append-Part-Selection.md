# Part Selection and Rationale

## Vision System

| Solution | Pros | Cons | Price |
|---|---|---|---:|
|![REALTEK AMB82 MINI IOT AI CAMERA](../assets/Realtek_AMB82.png)<br>[**REALTEK AMB82 MINI IOT AI CAMERA**](https://www.amazon.com/studio-Realtek-AMB82-Mini-Camera-Arduino/dp/B0CRYQ84RX) | - On-board AI object detection software<br>- Wide-angle lens allows for full vision of pipe ahead<br>- High-resolution camera with fast frame rates allows for quick real-time object detection | - Focal length is non-adjustable and set for long distance<br>- Short custom data cable means the entire module will need a unique mounting solution | $30 |
|![OV5640 CAMERA](../assets/OV5640.png)<br>[**OV5640 CAMERA XIAO ESP32S3 SENSE**](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/114993115/21277047)| - Familiarity with platform allows for more focus on object detection development time<br>- Long data cable allows for better mounting solution<br>- High resolution with fast frame rates<br>- Minimum focal length is about 10 cm, allowing for better inspection of small pipes<br>- Low cost<br>- Uses ESP32-S3 chip for on-board object detection | - Less RAM than other options | $24 |
|![m5stack](../assets/m5stack.png)<br>[**M5Stack**](https://shop.m5stack.com/products/m5stack-unitv2-m12-version-with-cameras) | - Highest processing power of any option<br>- High resolution and high frame-rate video<br>- On-board object-detection models preconfigured for common applications | - Bulky<br>- Way out of budget<br>- High power cost | $95 |

### Choice

[**OV5640 CAMERA XIAO ESP32S3 SENSE**](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/114993115/21277047) — upgrade to [previously used module](https://www.digikey.com/en/products/detail/seeed-technology-co-ltd/113991115/18724504)

### Rationale

The camera provides excellent video resolution and frame rate at a very low cost compared to the other options. It is also familiar to our team, so it will cut down on the amount of time needed to write the necessary software.

---

## Drive System

| Solution | Pros | Cons | Price |
|---|---|---|---:|
| ![NFP-GM25](../assets/NFP-GM25.png)<br>[**NFP-GM25-310-OEN**](https://www.amazon.com/GM25-310-Photoelectric-Measuring-Two-Wheel-Balancing/dp/B0C2VDCC98) | - True optical encoder<br>- Stronger than N20<br>- 360 CPR provides good feedback<br>- 3.3/5 V encoder interface<br>- Multiple gear ratios<br>- Compact enough for the pipe robot<br>- Good balance of speed and torque | - Larger than N20<br>- Heavier than N20<br>- 4 mm shaft<br>- 7.4 V rather than 5 V<br>- More expensive than basic N20 motors | $15 |
| ![Planetary Gear Motor](../assets/PlanetaryGearMotor.png)<br>**Planetary Gear Motor with Optical Encoder** | - Very high torque<br>- Planetary gearbox<br>- Optical encoder<br>- Available in 6 V<br>- Excellent for heavier robots<br>- Strong gearbox<br>- Good positional accuracy | - 36 mm diameter<br>- Much heavier<br>- Could be difficult to fit inside a 4-inch pipe<br>- Higher current requirements<br>- More expensive | $20 |
| ![GM37-520](../assets/GM37-520.png)<br>[**GM37-520**](https://www.amazon.com/CHR-GM37-520-Off-Axis-Torque-Reducer-Gearbox/dp/B0CMT1382X?th=1) | - High torque<br>- Metal gearbox<br>- Optical encoder versions available<br>- Many gear ratios<br>- Good for heavier robots<br>- Stronger shaft and gearbox | - 37 mm diameter<br>- Large for a 4-inch pipe<br>- Heavy<br>- Typically 12 V<br>- Higher power consumption<br>- More motor than the robot probably needs | $40 |
| ![Rob-28633](../assets/ROB-28633.png)<br>[**ROB-28633**](https://www.digikey.com/en/products/detail/sparkfun-electronics/ROB-28633/26523963) | - Compact and lightweight<br>- Built-in Hall-effect encoder<br>- 882 counts/revolution<br>- Good speed and torque for its size<br>- 31.5:1 gear ratio<br>- Good for ESP32 control<br>- Fits well in a 4–6 inch pipe | - Encoder is magnetic, not optical<br>- Limited torque compared with larger motors<br>- Wheel slip can affect distance accuracy<br>- Small gearbox can be damaged if stalled<br>- Requires a motor driver | $9.90 |

### Choice

[**SparkFun ROB-28633 N20 Motor With Encoder**](https://www.digikey.com/en/products/detail/sparkfun-electronics/ROB-28633/26523963)

### Rationale

The ROB-28633 was selected because its compact N20 form factor makes it well suited for the 4–6 inch pipe inspection robot. The integrated Hall-effect encoder provides 882 counts per revolution for accurate motor speed and distance feedback. Its 31.5:1 gear ratio provides a good balance between speed and torque, while its small size and low weight help keep the robot compact and maneuverable. The motor is also compatible with the ESP32 control system and is available as a matched pair for the two-wheel drive system.

---

## Drive Sensing

| Solution | Pros | Cons | Price |
|---|---|---|---:|
| ![MicoAir MTF-02P](../assets/MTF-02P.png)<br>[**MicoAir MTF-02P**](https://www.amazon.com/MicoAir-Optical-MTF-02P-Compatible-Ardupilot/dp/B0DM67PB1K) | - Optical flow + range in one<br>- 6 m range<br>- Very small and lightweight<br>- 5 V operation<br>- 50 Hz output<br>- UART communication | - More expensive than basic optical-flow sensors<br>- Requires UART programming<br>- Optical flow requires adequate lighting | $28 |
| ![Holybro PMW3901](../assets/PMW3901.png)<br>**Holybro PMW3901** | - Small and lightweight<br>- Good optical-flow tracking<br>- 95 Hz output<br>- UART interface<br>- Low power consumption<br>- Easy to integrate | - No built-in distance sensor<br>- Requires a separate range sensor<br>- Less functionality than the MTF-02P | $20.59 |
| ![Holybro H-Flow](../assets/H-Flow.png)<br>**Holybro H-Flow** | - Optical flow + distance sensor<br>- Up to 30 m range<br>- Built-in 6-axis IMU<br>- Works in low-light conditions<br>- CAN/DroneCAN communication<br>- Very capable sensor | - Much more expensive<br>- Heavier at 15.2 g<br>- More complicated than needed<br>- Larger than the MTF-02P | $145 |

### Choice

[**MicoAir Optical Flow & Range Sensor MTF-02P**](https://www.amazon.com/MicoAir-Optical-MTF-02P-Compatible-Ardupilot/dp/B0DM67PB1K)

### Rationale

The MTF-02P was selected because it combines optical flow and distance measurement into one compact and lightweight sensor. Its 6 m range, 50 Hz output, and 5 V operation make it well suited for the pipe inspection robot. Using one sensor for both functions reduces the number of components and saves space, while providing movement and distance data that can work with the N20 motor encoders to improve the robot’s navigation and return-to-start accuracy.

---

## Chassis

| Solution | Pros | Cons | Price |
|---|---|---|---:|
| ![Mini RC Truck](../assets/GreenMonster.png)<br>[**Mini RC Truck, 1:64 Scale Monster Truck**](http://amazon.com/gp/aw/d/B0DMW81N1H/?_encoding=UTF8&pd_rd_plhdr=t&aaxitk=9cc0125e62e2c5a25db58d004f249b14&hsa_cr_id=0&qid=1772599395&sr=1-1-9e67e56a-6f64-441f-a281-df67fc737124&ref_=sbx_s_sparkle_sbtcd_asin_0_title&pd_rd_w=wBchM&content-id=amzn1.sym.9f2b2b9e-47e9-4764-a4dc-2be2f6fca36d%3Aamzn1.sym.9f2b2b9e-47e9-4764-a4dc-2be2f6fca36d&pf_rd_p=9f2b2b9e-47e9-4764-a4dc-2be2f6fca36d&pf_rd_r=ESK7BKKDKWR7T78W6JFN&pd_rd_wg=DVVPd&pd_rd_r=beebd90e-6403-4bb7-b0e6-e4d8515845a8&th=1) | - Fits within 4-inch pipe with its cosmetics attached<br>- Allows room to attach components with cosmetic shell removed<br>- Trailer hitch can be used to attach rescue line without modification<br>- Off-road tires allow for easy traversal of pipes | - Uses generic remote with limited range (30 m)<br>- Limited battery life (20 minutes)<br>- High price means only one can be bought for prototyping | $18 each |
| ![Mini CyberTruck](../assets/CyberStuck.png)<br>[**Mini RC Truck, 1:64 Scale Monster Truck Remote Control Car with Lights**](https://www.amazon.com/DDZOOU-Mini-Truck-Rechargeable-Adjustable/dp/B0F8QVP1JB/ref=sr_1_1_sspa?crid=31093XAH4DH2A&dib=eyJ2IjoiMSJ9.R5lU3AIb3UESFJX85B1DEAUXQZDKsg6tbDXb7izM6PXezVQTlx4gHxhxyy2nQdPkcscnMcD2azL1drdtaxoqxo2nt1JnSSUoA5UZnRY9myeQqGAtAVv_amOiidoQYnvWivE7ApjBfwVmsY9BTT7VUZaV1DpzfJoTWPng86WB-jHzmTSENxD-uNW7npG8iSVLCYA0o-bBeolxr9Eb_LbWdhtHWSytYBhW_nAFB9Lsnj2dl-_003bwqLaJad5EuSpueuYVECPhYuc00BYo4OVHGw_ri3We64K_9CK5OR_zvIo.IWu29MUciEHtHukflzQ3klrPCYm1Sj5ni4Cdg_wvDO4&dib_tag=se&keywords=micro%2Brc%2Btruck&qid=1772599395&sprefix=micro%2Brc%2Btruck%2Caps%2C189&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1) | - Allows more room to attach components with cosmetic shell removed<br>- Trailer hitch can be used to attach rescue line without modification<br>- Off-road tires allow for easy traversal of pipes<br>- Can use phone app instead of remote | - Taller than needed (4.1 inches)<br>- Uses generic remote with limited range (30 m)<br>- Limited battery life (20 minutes)<br>- High price means only one can be bought for prototyping<br>- Phone app has very limited range | $19 each |
| ![Mini Tank](../assets/GrayTank.png)<br>[**2.4GHz Mini RC Tank Toy with LED and Rotating Turret**](https://www.amazon.com/2-4GHz-Rotating-Turret-Ultimate-Military/dp/B0D6G82XWM/ref=sr_1_6?crid=1VYBVR3EA2PX9&dib=eyJ2IjoiMSJ9.OJM5_Xao0IyzGW_jRRWdjvUSvdJLoBGJxXR3RYr7zeoT2epLGY-q0SHrv8c4em_vGZyYOqbS2usZCW5CrwC0TDSBQek8LimjynuGk4_GaNC0NErUgB-mOCefmE-UkdsEZBvBtRN1835zMm-ojcNW9rT01hpYw0q3QDOgziHxeTG75OhqbGi5ZfCFM5wP0mifkVFNYycAIT4US7rKStEXepHygCp00y7m3Sy9rgrYPmxywPEa5WSHgqLwdc-ZpHes7tB9G0kYoWNCYCmUcQ_sCAywI28LWdsajvABeB0G6Tc.pvK_RL0quRfn_FfkvnD1E47qTfoTwk7bct1sldSNA60&dib_tag=se&keywords=micro%2Brc%2Btank&qid=1772600293&sprefix=micro%2Brc%2Btank%2Caps%2C196&sr=8-6&th=1) | - Flat chassis allows for stable platform to build from<br>- Rotating turret could be utilized to give a 360° camera view<br>- Treads allow for easier traversal of rough terrain | - High price point makes any testing or modification risky because duplicates cannot be afforded<br>- Turret mechanism is difficult to disassemble carefully<br>- Paying for unneeded features such as speakers | $23 each |

### Choice

[**2.4 GHz Mini RC Tank Chassis**](https://www.amazon.com/2-4GHz-Rotating-Turret-Ultimate-Military/dp/B0D6G82XWM/ref=sr_1_6?crid=1VYBVR3EA2PX9&dib=eyJ2IjoiMSJ9.OJM5_Xao0IyzGW_jRRWdjvUSvdJLoBGJxXR3RYr7zeoT2epLGY-q0SHrv8c4em_vGZyYOqbS2usZCW5CrwC0TDSBQek8LimjynuGk4_GaNC0NErUgB-mOCefmE-UkdsEZBvBtRN1835zMm-ojcNW9rT01hpYw0q3QDOgziHxeTG75OhqbGi5ZfCFM5wP0mifkVFNYycAIT4US7rKStEXepHygCp00y7m3Sy9rgrYPmxywPEa5WSHgqLwdc-ZpHes7tB9G0kYoWNCYCmUcQ_sCAywI28LWdsajvABeB0G6Tc.pvK_RL0quRfn_FfkvnD1E47qTfoTwk7bct1sldSNA60&dib_tag=se&keywords=micro%2Brc%2Btank&qid=1772600293&sprefix=micro%2Brc%2Btank%2Caps%2C196&sr=8-6&th=1)

### Rationale

The tank chassis was selected because its treads provide better traction and reduce slipping compared to wheeled chassis. The flat chassis provides a stable platform for mounting the ESP32, motor driver, sensors, and battery, while the compact design allows the robot to traverse rough and uneven surfaces inside the pipe.

---

## Motor Controller

| Solution | Pros | Cons | Price |
|---|---|---|---:|
| ![DRV8833PWPR](../assets/DRV8833.png)<br>[**DRV8833PWPR**](https://www.digikey.com/en/products/detail/texas-instruments/DRV8833PWPR/2743167?msockid=2aa431d6e20468cc094d263ae36269aa) | - Surface-mount HTSSOP package<br>- Controls 2 DC motors<br>- 1.5 A output per channel<br>- Compact and lightweight<br>- Works directly with ESP32 PWM signals<br>- Low cost | - Motor supply limited to 10.8 V<br>- Less current capability than DRV8848 | $3.02 |
| ![TB6612FNG](../assets/TB6612.png)<br>**TB6612FNG** | - Surface-mount 24-SSOP package<br>- Controls 2 DC motors<br>- Up to 1 A continuous per channel<br>- Motor voltage up to 13.5 V<br>- Low power consumption<br>- Inexpensive | - Larger package than DRV8833<br>- Lower current capability<br>- Operating temperature is only -20°C to 85°C | $2.04 |
| ![DRV8848PWPR](../assets/DRV8848.png)<br>[**DRV8848PWPR**](https://www.digikey.com/en/products/detail/texas-instruments/DRV8848PWPR/6571780?msockid=2aa431d6e20468cc094d263ae36269aa) | - Surface-mount HTSSOP package<br>- Controls 2 DC motors<br>- Up to 2 A per bridge / 4 A parallel<br>- Motor voltage 4–18 V<br>- More current capacity and voltage headroom<br>- Built-in protection features | - More capability than the small N20 motors require<br>- Slightly more expensive<br>- More complex than necessary for this project | $2.97 |

### Choice

[**DRV8833PWPR Motor Driver**](https://www.digikey.com/en/products/detail/texas-instruments/DRV8833PWPR/2743167?msockid=2aa431d6e20468cc094d263ae36269aa)

### Rationale

The DRV8833PWPR was selected because it can operate with a 5 V motor supply, supports two DC motors, and can be soldered directly to the PCB using its surface-mount package. Its compact size, low cost, and compatibility with the ESP32 make it well suited for controlling the two N20 motors while keeping the robot’s electronics compact.
