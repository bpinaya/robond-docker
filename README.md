# Udacity RoboND Docker container

[//]: # (Image References)


[all]: ./img/readme5.png "All installed"
[1]: ./img/readme5.png "1"
[2]: ./img/readme5.png "2"
[3]: ./img/readme5.png "3"
[4]: ./img/readme5.png "4"

![alt text][all]
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



## Using your container
After you've run that command, you'll probable wait for the container to download, then you'll see an output like this:
![alt text][1]


then, open your favorite browser (Chrome is prefered, but tested in Firefox) and navigate to:
```
localhost:6080
```
or
```
127.0.0.1:6080
```
and you should see your desktop like this:
![alt text][2]

And there you have it! Your own 16.04 with everything you need to get working installed.
## Running your second assigment

As you've seen in the lessons, you need to navigate and create your work environment, but this is already done for you. Right now, you'll need 4 terminals (Also we'll run the demo here, so remember to set the `demo` value in `inverse_kinematics.launch` to `true`). You can open terminals like this:
![alt text][3]
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
![alt text][4]

**NOTE** Be aware of your files, if you load docker with your local volumes you'll be able to save your changes, otherwise you'll have to commit your changes to your favorite Content Managment System (Github ;) )


## Todos

 - Support local container save (right now you can use docker commit, but be aware)
 - Add other Udacity Assigments.
 - ? ask me for more things you'll like to see here

## Acknowledgements
 - This image is based on [FCWU image](https://github.com/fcwu/docker-ubuntu-vnc-desktop) , that has the support for the VNC server with browser support, so no VNC client is needed, kudos to him!
 - OSRF Dockerfiles, that helped me shape this image to the needs.
 - The Udacity folks, for all their support.
