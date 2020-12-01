# PSn00bSDK Docker Bundle MIPS Compilator

## Requirements
- Docker
- Docker Compose
## Deployments
Start the container
```sh
docker-compose up -d
``` 
Your project has to be in the psxproj folder with makefile<br>
<b>Don't touch the setup.mk file !</b>

This CLI is for compiling your project
```sh
docker exec -it psn00b_container make
```
## Debug purposes
Access to the container in bash
```sh
docker exec -it psn00b_container bash
```
## Credits
- NahimR - Docker Bundle
- Lameguy64 - <a href="https://github.com/Lameguy64/PSn00bSDK">PSn00bSDK</a>
