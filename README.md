[![Docker Stars](https://img.shields.io/docker/stars/bpinaya/robond-docker.svg)](https://hub.docker.com/r/bpinaya/robond-docker/)
[![Docker Pulls](https://img.shields.io/docker/pulls/bpinaya/robond-docker.svg)](https://hub.docker.com/r/bpinaya/robond-docker/)

# Udacity RoboND Docker container

[//]: # (Image References)	

[image0]: ./img/redme5.png "All installed"
[image1]: ./img/redme1.png "1"
[image2]: ./img/redme2.png "2"
[image3]: ./img/redme3.png "3"
[image4]: ./img/redme4.png "4"
[imagewin]: ./img/imagewin.png "imagewin"
![alt text][image0]
This is a Docker Container for Udacity's Robotics Nanodegree, it'll allow you to run Assigment 2 on your browser from any OS:
  - Linux (Tested in Ubuntu 14.04)
  - Windows (To be tested)
  - MacOS (To be tested)

This container was born out of need, since I need 14.04 in my computer but needed ROS Kinetic for this assigment, and VMware just doesn't do it for me. Feel free to submit PR and file bugs if you encounter them.
## Set up

You'll need to install Docker in your computer, if you've used Docker before this step should be straight forward, otherwise check [this link](https://www.docker.com/what-docker) for more information about it.
  - Installation's instructions for Ubuntu can be found [HERE](https://docs.docker.com/engine/installation/linux/ubuntu/)
  - Installation's instructions for Windows can be found [HERE](https://docs.docker.com/docker-for-windows/install/)
  - Installation's instructions for Windows can be found [HERE](https://docs.docker.com/docker-for-mac/install/)

After you have Docker installed, running the container should be as easy as typing:
```bash
docker run -it --rm -p 6080:80 bpinaya/robond-docker
```
in your terminal (Note that in Ubuntu, if not set up properly, you'll need sudo to run the container).

If you want to use a VNC client (Like [RealVNC](https://www.realvnc.com/download/viewer/)), try running this line:
```bash
docker run -it --rm -p 6080:80 -p 5900:5900 bpinaya/robond-docker
```
Then open it in your VNC viewer with the port 5900.

**NOTE** If you are using Windows, you might want to figure out the IP that it gives to Docker, it's easy, if you open your Docker terminal it should be within the first lines, like this:

![alt text][imagewin]

As you can see, the IP for that docker is ` 192.168.99.100` . So navigate to ` 192.168.99.100:6080` if you are using the browser option.

## Using your container
After you've run that command, you'll probable wait for the container to download, then you'll see an output like this:
![alt text][image1]


then, open your favorite browser (Chrome is prefered, but tested in Firefox) and navigate to:
```
localhost:6080
```
or
```
127.0.0.1:6080
```
and you should see your desktop like this:
![alt text][image2]

And there you have it! Your own 16.04 with everything you need to get working installed.
## Running your second assigment

As you've seen in the lessons, you need to navigate and create your work environment, but this is already done for you. Right now, you'll need 4 terminals (Also we'll run the demo here, so remember to set the `demo` value in `inverse_kinematics.launch` to `true`). You can open terminals like this:
![alt text][image3]
In the first terminal type:
```
roslaunch kuka_arm target_description.launch
```
In the second one type:
```
roslaunch kuka_arm cafe.launch
```
In the thrid one type:
```
roslaunch kuka_arm spawn_target.launch
```
And lastly in the fourth one:
```
roslaunch kuka_arm inverse_kinematics.launch
```

And that's it!!! You have your environment running wherever you want. As you might have noticed, running this 4 commands in 4 different windows in the same than running your `safe_spawner.sh` script, but running that won't work, I am trying to figure out why, then again this repo will improve, and eventually add all the assigments. Check that you see this:
![alt text][image4]

**NOTE** Be aware of your files, if you load docker with your local volumes you'll be able to save your changes, otherwise you'll have to commit your changes to your favorite Content Managment System (Github ;) )


## Todos

 - Support local container save (right now you can use docker commit, but be aware)
 - Add other Udacity Assigments.
 - ? ask me for more things you'll like to see here

## Acknowledgements
 - This image is based on [FCWU image](https://github.com/fcwu/docker-ubuntu-vnc-desktop) , that has the support for the VNC server with browser support, so no VNC client is needed, kudos to him!
 - OSRF Dockerfiles, that helped me shape this image to the needs.
 - The Udacity folks, for all their support.
