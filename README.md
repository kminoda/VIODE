# VIODE
This is a repository for the VIODE (Visual-Inertial Odometry in Dynamic Environments) dataset described in the paper:

Koji Minoda, Fabian Schilling, Valentin Wüest, Dario Floreano, and Takehisa Yairi, "VIODE: A Simulated Dataset to Address the Challenges of Visual-Inertial Odometry in Dynamic Environments", IEEE Robotics and Automation Letters (RA-L), 2021.

The overall documentation is available in the above RA-L paper. 

[Data download here (A link to Zenodo)](https://zenodo.org/record/4493401)

[YouTube link Here]

# Dataset Structure
The visual-inertial sensor data is provided in ROS bag format. Each bag contains the following topics.
- /cam0/image_raw
- /cam1/image_raw
- /cam0/segmentation
- /cam1/segmentation
- /imu0
- /odometry

The first two topics contain RGB image data. Since these are captured in the simulator, we also provide ground-truth extrinsic and intrinsic parameters for this stereo setup.

The next two topics are the ground truth semantic segmentation provided by AirSim. 
The ex-/intrinsic parameters are the same as the ones with the RGB images. 
We also provide rgb_id.txt which contains the correspondence between object ID and RGB value in segmentation images.

The other files are
- calibration.yaml
- rgb_id.txt

The calibration.txt provides extrinsic and intrinsic parameters of two cameras. 
Note that the format follows that of [VINS-Fusion](https://github.com/HKUST-Aerial-Robotics/VINS-Fusion), one of the state-of-the-art VIO algorithms.
The rgb_id.txt provides the correspondence between object ID and RGB value in segmentation images.

