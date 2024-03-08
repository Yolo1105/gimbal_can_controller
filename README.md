# Add a public/private key pair
ssh-keygen -t ed25519 -C "<comment>"
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/yolo/.ssh/id_ed25519):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/yolo/.ssh/id_ed25519
Your public key has been saved in /home/yolo/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:+XtdvOcyIhKeYNjHOz1ME4/L5ovZU3y02UoLrEcbiGE test
The key's randomart image is:
+--[ED25519 256]--+
|                 |
|                 |
|                 |
|        E..   .  |
|     o oSo B . = |
|    . + =.= O = +|
|     . + O.* B +.|
|        *+@.= *..|
|        o==B . +o|
+----[SHA256]-----+

yolo@Mohan:~$ cd /home/yolo/.ssh/
yolo@Mohan:~/.ssh$ ls
id_ed25519  id_ed25519.pub  known_hosts
yolo@Mohan:~/.ssh$ cat id_ed25519
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACCxlpUc8D3udpx48o8VIZvcO3OzwkZftr3JIHpOQ/IGjwAAAIglioafJYqG
nwAAAAtzc2gtZWQyNTUxOQAAACCxlpUc8D3udpx48o8VIZvcO3OzwkZftr3JIHpOQ/IGjw
AAAEANHqLjm05HH9jhxa10tP4Rv5GaMmpLtAFCsoJ2kOvimbGWlRzwPe52nHjyjxUhm9w7
c7PCRl+2vckgek5D8gaPAAAABHRlc3QB
-----END OPENSSH PRIVATE KEY-----
yolo@Mohan:~/.ssh$ cat id_ed25519.pub
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAILGWlRzwPe52nHjyjxUhm9w7c7PCRl+2vckgek5D8gaP test

yolo@Mohan:~/.ssh$ git clone git@gitlab.com:nyu-robomaster/controls_ros.git
Cloning into 'controls_ros'...
remote: Enumerating objects: 1811, done.
remote: Counting objects: 100% (103/103), done.
remote: Compressing objects: 100% (102/102), done.
remote: Total 1811 (delta 64), reused 0 (delta 0), pack-reused 1708
Receiving objects: 100% (1811/1811), 2.88 MiB | 19.64 MiB/s, done.
Resolving deltas: 100% (1089/1089), done.

yolo@Mohan:~/.ssh$ mv controls_ros/ ../ros2_iron/

yolo@Mohan:~/ros2_iron/controls_ros/src$ git checkout ml7612-nightly
Branch 'ml7612-nightly' set up to track remote branch 'ml7612-nightly' from 'origin'.
Switched to a new branch 'ml7612-nightly'

yolo@Mohan:~/ros2_iron/controls_ros/src$ cd uv_utils

geometry_msgs::msg::Twist message;
message.x = something;
twist_to_CAN(message);

cd controls_ros
colcon build
source install/setup.bash
ros2 run uv_utils GCC
