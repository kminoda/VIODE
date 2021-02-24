# The VIODE dataset
This is a repository for the VIODE (Visual-Inertial Odometry in Dynamic Environments) dataset described in the paper:

Koji Minoda, Fabian Schilling, Valentin Wüest, Dario Floreano, and Takehisa Yairi, **VIODE: A Simulated Dataset to Address the Challenges of Visual-Inertial Odometry in Dynamic Environments**, IEEE Robotics and Automation Letters (RA-L), 2021. [PDF](notyet)

The overall documentation is available in the above RA-L paper. If you use VIODE in academic work, please cite:
```
@article{minodaRAL2021,
  title={{VIODE}: A Simulated Dataset to Address the Challenges of Visual-Inertial Odometry in Dynamic Environments},
  author={Minoda, Koji, Schilling, Fabian, Wüest, Valentin, Floreano, Dario, and Yairi, Takehisa},
  journal={IEEE Robotics and Automation Letters},
  volume={},
  number={},
  pages={},
  doi = {},
  year={2021}
 }
```



A YouTube video for an introduction to the VIODE dataset:  
[![VIODE](http://img.youtube.com/vi/LlFTyQf_dlo/0.jpg)](https://youtu.be/LlFTyQf_dlo "VIODE")


# Dataset Link
Main ROS bag files are uploaded on Zenodo:  
[Data download here (A link to Zenodo)](https://zenodo.org/record/4493401)

The other two files can be downloaded from this repository.


# Dataset Structure
The visual-inertial sensor data is provided in ROS bag format. Each bag contains the following topics.
- `/cam0/image_raw`
- `/cam1/image_raw`
- `/cam0/segmentation`
- `/cam1/segmentation`
- `/imu0`
- `/odometry`

`/cam0/image_raw` and `/cam1/image_raw` contain RGB image data. Since these are captured in the simulator, we also provide ground-truth extrinsic and intrinsic parameters for this stereo setup.

`/cam0/segmentation` and `/cam1/segmentation` are the ground truth semantic segmentation provided by AirSim. 
The ex-/intrinsic parameters are the same as the ones with the RGB images. 

The other files are
- `calibration.yaml`
- `cam0_pinhole.yaml` & `cam1_pinhole.yaml`
- `rgb_id.txt`
- `vehicle_ids_*.txt`

The `calibration.yaml`, `cam0_pinhole.yaml`, and `cam1_pinhole.yaml` provide extrinsic and intrinsic parameters of two cameras. 
Note that the format follows that of [VINS-Fusion](https://github.com/HKUST-Aerial-Robotics/VINS-Fusion), one of the state-of-the-art VIO algorithms.
The `rgb_id.txt` provides the correspondence between object ID and RGB value in segmentation images.
The `vehicle_ids_*.txt` contains the correspondence between object ID and object name for each environment. Object name also indicates whether the vehicle is whether dynamic or static.
