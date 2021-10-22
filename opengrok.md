#version
## /opengrok/lib# diff opengrok.jar opengrok-1.7.21.jar

#cmd
sudo docker run -d  --name opengrok -p 80:8080/tcp -e SYNC_PERIOD_MINUTES="720" -v <path/to/your/src>:/opengrok/src/ -e INDEXER_OPT="--disableRepository git -m 4096 -v"  opengrok/docker:latest

#option info
##java -jar /opengrok/lib/opengrok.jar

  --disableRepository type_name
        Disables operation of an OpenGrok-supported repository. See also
        -h,--help repos. Option may be repeated.
          Ex: --disableRepository git
              will disable the GitRepository
          Ex: --disableRepository MercurialRepository

  -m, --memory number
        Amount of memory (MB) that may be used for buffering added documents and
        deletions before they are flushed to the directory (default 16.0).
        Please increase JVM heap accordingly too.
        
#other
https://oracle.github.io/opengrok/
https://github.com/oracle/opengrok/wiki/Python-scripts-transition-guide
