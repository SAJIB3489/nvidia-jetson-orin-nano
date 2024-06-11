# nvidia-jetson-orin-nano

Here, I will write the information about my current project with **NVIDIA Jetson Orin Nano Developer Kit**



## Error and Solution

**1. Staring the container and pull the image first time on Orin**

```
$ sudo docker run --runtime nvidia -it --rm --network host --volume ~/nvdli-data:/nvdli-nano/data --device /dev/video0 nvcr.io/nvidia/dli/dli-nano-ai:v2.0.3-r36.3.0


docker: unknown server OS: .
See 'docker run --help'.
```
```
$ systemctl status docker.service

Job for docker.service failed because the control process exited with error code.
See "systemctl status docker.service" and "journalctl -xeu docker.service" for details.
```

**Solution**

```
sudo update-alternatives --set iptables /usr/sbin/iptables-legacy
```
```
sudo apt reinstall docker-ce
```
