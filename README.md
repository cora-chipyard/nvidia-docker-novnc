![Preview Image](https://cdn-images-1.medium.com/max/1600/1*wKNrdA3rqpHZU82DU4gVPA.gif)

### Building a GPU-enhanced Lubuntu Desktop with nvidia-docker2

This is the remote solution to start a ros machine with a car simulator. [Will Kessler's solution](https://engineering.udacity.com/creating-a-gpu-enhanced-virtual-desktop-for-udacity-497bdd91a505) is outdated, and this solution is valid in December, 2020.

### Build up the container
To build on a plain vanilla Google Compute GPU host:

1. Spin up a GC GPU host on the google console.  Make sure it has at least one Tesla K80 GPU, and decent amount of VCPUs (e.g. 4, and enough disk space, at least 50Gb). GPU availablity can be check from google docs or cora integration docs, our demo machine is deployed in `us-central1-a` zone.
2. Upload this repo and unpack it in `/root/build` or wherever you like as a temporary location.
3. Run `preinstall.sh`. This just runs `apt-get update` and puts in `screen` and `emacs` for getting started.
4. Run `build.sh`. This will build everything needed to start up a nvidia-docker2 container with Ubuntu 16.04 and Lubuntu desktop.

![SetupImage1](https://user-images.githubusercontent.com/176268/38177239-00283584-35b3-11e8-9c84-4f788120caca.png)
![Setupimage2](https://user-images.githubusercontent.com/176268/38177244-0b6b4d3c-35b3-11e8-8605-ed184afa59a6.png)

### Running the container

To run the container on this host, use `run.sh`. Note that NoVNC will
expect connections on port 40001. Then surf to your host on that port.

### Setting up network access

When executing /run.sh, the output ends in something like this:

```
http://5e1e573deXYZ:40001/vnc.html?host=5e1e573deXYZ&port=40001
```

navigate to

```
navigating to http://<your ip>:40001/vnc.html?host=<your ip>&port=40001
```

### More info

For more links and reference, please see the Medium posting about this environment [here](https://engineering.udacity.com/creating-a-gpu-enhanced-virtual-desktop-for-udacity-497bdd91a505).
