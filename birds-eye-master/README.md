# birds-eye
A bird's-eye view is an elevated view of an object from above, with a perspective as though the observer were a bird. Some artifacts in the game field block the drivers view in front of the robot; therefore, a view with the ability to see distance and object is necessary. Bird's eye view is one way to eliminate driver mistake and easily align the robot and capture objects.

Procedure:
1. Either clone the repository or download the zip file
2. Few Dependencies need to be downloaded before the startup of bird's eye view
```
sudo apt install python3
sudo apt install python3-pip
pip3 install flask
pip3 install opencv-python
```
**: DO NOT INSTALL OPENCV-PYTHON IF USING NVIDIA JETSON**
  - Nvidia Jetson already has an opensource library of opencv specificillay for the jetson's use
3. Edit few lines of code for the purpose of "correct directory"
  - In the python file BirdEye.py change these three variables: 
  
    northFile = file path of north_transformation.npy
    
    southFile = file path of south_transformatoin.npy
    
    portFile = file path of port.npy
    ```
    northFile = "/Users/sonifamily/Documents/BirdEyeProject/north_transformation.npy"
    southFile = "/Users/sonifamily/Documents/BirdEyeProject/south_transformation.npy"
    portFile = "/Users/sonifamily/Documents/BirdEyeProject/port.npy"
    ```
  - In the same python file BirdEye.py, you may edit the port number to which your local host is displaying to
      ```
      if __name__ == '__main__':
        app.run('0.0.0.0',debug = True,port = 5802) #enter port number#
      ```
4. ALL set!!! Run your python file from the terminal and go to http://0.0.0.0:5802 #change port#
  - To visit settings page: http://0.0.0.0:5802/setting
  
 Specifications of Setting Page:
 Setting page allows you to calibrate your cameras and change usb port for the camera

Run python script on reboot:
```
sudo nano /etc/rc.local
sudo python #location of python script
```
