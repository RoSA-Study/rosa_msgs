# rosa_msgs
Custom ROS Messages for the RoSA project

If you found the code useful, you can cite the corresponding paper:

Citation (bibtex)
@article{Strazdas_2022, doi = {10.3390/s22030923}, url = {https://doi.org/10.3390%2Fs22030923}, year = 2022, month = {jan}, publisher = {{MDPI} {AG}}, volume = {22}, number = {3}, pages = {923}, author = {Dominykas Strazdas and Jan Hintz and Aly Khalifa and Ahmed A. Abdelrahman and Thorsten Hempel and Ayoub Kassim Al-Hamadi}, title = {Robot System Assistant ({RoSA}): Towards Intuitive Multi-Modal and Multi-Device Human-Robot Interaction}, journal = {Sensors} } 

MDPI and ACS Style

Strazdas, D.; Hintz, J.; Khalifa, A.; Abdelrahman, A.A.; Hempel, T.; Al-Hamadi, A.K. Robot System Assistant (RoSA): Towards Intuitive Multi-Modal and Multi-Device Human-Robot Interaction. Sensors 2022, 22, 923. https://doi.org/10.3390/s22030923
AMA Style

Strazdas D, Hintz J, Khalifa A, Abdelrahman AA, Hempel T, Al-Hamadi AK. Robot System Assistant (RoSA): Towards Intuitive Multi-Modal and Multi-Device Human-Robot Interaction. Sensors. 2022; 22(3):923. https://doi.org/10.3390/s22030923
Chicago/Turabian Style

Strazdas, Dominykas, Jan Hintz, Aly Khalifa, Ahmed A. Abdelrahman, Thorsten Hempel, and Ayoub K. Al-Hamadi. 2022. "Robot System Assistant (RoSA): Towards Intuitive Multi-Modal and Multi-Device Human-Robot Interaction" Sensors 22, no. 3: 923. https://doi.org/10.3390/s22030923

# Types
Custom ROS Messages for the RoSA project

    FacialData.msg
    	Contains information about the detected face
	face		sensor_msgs/CompressedImage	--> Detected face 
	camID		int8 
	user		int8				--> User Id
	user_name	string				--> User name 
	user_score	float64				--> Detection score 
	emoji		string				--> Recognized facial emotion 
	emoji_score	float64				--> Recognized facial emotion score
	xmin		int64				--> Face boundary box top-left point (xmin, ymin) wrt original frame    
	ymin		int64 
	xmax		int64				--> Face boundary box bottom-right point (xmax, ymax) wrt original frame 
	ymax		int64 
	cx		float64				--> Face boundary box center point (cx, cy)
	cy		float64 
	roll		float64				--> Estimated head pose roll angle 
	pitch		float64				--> Estimated head pose pitch angle  
	yaw		float64				--> Estimated head pose yaw angle  
	left_hand	bool 				
    FacialHeader.msg
    	Contains information about the current frame 
	framesensor_msgs/Compressed	Image 		--> Current frame
	ids				int8[] 		--> Detected ids in Image
	facialData			FacialData[] 	--> Array of facialData, size = no of ids

	Cube.msg:
        letters     string
        color       string
        x           float
        y           float
        layer       int
	ProjectionObject.msg
    Joint.msg   
        Contains Kinect v2 Joint: JointType, X,Y,Z as float
	
	JointType:
        SpineBase = 0,
        SpineMid = 1,
        Neck = 2,
        Head = 3,
        ShoulderLeft = 4,
        ElbowLeft = 5,
        WristLeft = 6,
        HandLeft = 7,
        ShoulderRight = 8,
        ElbowRight = 9,
        WristRight = 10,
        HandRight = 11,
        HipLeft = 12,
        KneeLeft = 13,
        AnkleLeft = 14,
        FootLeft = 15,
        HipRight = 16,
        KneeRight = 17,
        AnkleRight = 18,
        FootRight = 19,
        SpineShoulder = 20,
        HandTipLeft = 21,
        ThumbLeft = 22,
        HandTipRight = 23,
        ThumbRight = 24
    Body.msg
        Contains Kinect v2 Joints as Joint[], IsTracked as bool?
	
    KinectBodies.msg
        Contains Kinect v2 Bodies as Body[]
	
    Environment.msg
    	Contains Cube[] messages about the current state of the cubes
	
	Cube[] CubeStatus
	Cube[] HalfSpaces

# How to install
cd ~/catkin_ws/src

git clone https://github.com/RoSA-Study/rosa_msgs.git

cd ..

catkin_make

source devel/setup.bash

rosmsg package rosa_msgs

