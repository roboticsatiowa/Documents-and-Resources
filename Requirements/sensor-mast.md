# Rover Sensor Mast

This project involves designing, building, and programming a "mast" for the rover (see images below for examples). This mast is important to the rover for a variety of reasons. Until now we have been relying on fixed cameras for video data. This means that in order to get good coverage of the rover we need many different cameras. It also means any expensive specialty sensors such as IR cameras and depth cameras must be pointed in a fixed location. 



## Requirements
- **Mandatory**
  - Capable of 360 degrees of rotation (Doesn't need to be continuous)
  - Contain controllable 2 axis gimble: Up/down, Left/right
  - Able to fit in university van
  - Contain 1 or more cameras that can be read from the Jetson
  - Able to see in visible spectrum
  - Able to see 960nm near-infrared 
  - Autonomously identify aruco markers (This has already been done. You may "borrow" the code)
- **Optional**
  - Infrared camera
  - Stereo camera
  - Waterproof
  - Absolute positioning (closed loop) so camera data may be used for mapping
  - Camera zoom and software camera settings control (iso, focus, white balance, etc.)
  - Capable of stitching together 360 degree panoramas (this has been mandatory in previous years. More information to come)
  - Automatically identify and translate Mandarin and Russian text.
- **Key Considerations**
  - How strong does this mast need to be? Will it survive a rollover? What about large bumps and vibrations?
  - How will we communicate with the sensors in the top? Will cables get twisted when it spins?
  - Remember the end goal. What is the purpose of this project? Always be scrutinizing if something is worth your time.
  - How heavy will this be? We have a mass budget of 50 Kg and are already walking the line.
  - It will be difficult to get this in the van. Is it easier to make this foldable or removable? We only get 15 minutes to set up the robot and basestation.
  - Consider an engineered faliure point. A rollover is a likely event. Where can it break to minimize damage to the rest of the assembly





![](https://assets.science.nasa.gov/dynamicimage/assets/science/psd/mars/resources/detail_files/2/4/24223_PIA23316-web.jpg?w=1600&h=1068&fit=clip&crop=faces%2Cfocalpoint)

![](https://buymarsrovers.com/wp-content/uploads/2023/01/Mars_2020_Perseverance_Rover_Replica_mast_navcam_mastcam_supercam_standard-1024x576.jpg)

![](https://pds-atmospheres.nmsu.edu/data_and_services/atmospheres_data/PERSEVERANCE/images/meda_pic_2.png)

