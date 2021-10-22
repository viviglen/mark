#version
## /opengrok/lib# diff opengrok.jar opengrok-1.7.21.jar

#cmd
sudo docker run -d  --name opengrok -p 80:8080/tcp -e SYNC_PERIOD_MINUTES="720" -v <path/to/your/src>:/opengrok/src/ -e INDEXER_OPT="--disableRepository git -m 4096 -v"  opengrok/docker:latest
