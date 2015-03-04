cuda-ssh
========
Ubuntu Core 14.04 + CUDA 6.5.19 + SSH server. Requires the host has the corresponding CUDA drivers installed for the kernel module.

Build
-----
Include password.txt with the password for sshd (by default this is "password").

Usage
-----
The container must have all NVIDIA devices attached to it for CUDA to work properly.
Therefore the command will be as such: `docker run -dP --device /dev/nvidiactl:/dev/nvidiactl --device /dev/nvidia-uvm:/dev/nvidia-uvm --device /dev/nvidia0:/dev/nvidia0 kaixhin/cuda-ssh`.
With 4 GPUs this would also have to include `--device /dev/nvidia1:/dev/nvidia1 --device /dev/nvidia2:/dev/nvidia2 --device /dev/nvidia3:/dev/nvidia3`.

For automatically mapping a SSH port use `docker run -dP kaixhin/cuda-ssh` and `docker port <id>` to retrieve the port.
For specifying the port manually use `docker run -d -p <port>:22 kaixhin/cuda-ssh`.
The shell can be entered as usual using `docker run -it kaixhin/cuda-ssh bash`.