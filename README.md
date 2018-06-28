# Docker container for the Citrix Receiver Client

This is a simple container to run the Citrix Receiver using the firefox browser.

## How to build this docker image
```
docker build -t citrix_receiver .
```

## Start the container
```
docker run -d --name citrix_receiver citrix_receiver
```

## Connect to the container via ssh and X-Forward
Please set the WEB_URL_TO_LOGIN to your specific login url
```
ssh -f -X receiver@$(docker inspect --format '{{ .NetworkSettings.IPAddress }}' citrix_receiver) -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no /usr/bin/firefox <WEB_URL_TO_LOGIN> > /dev/null 2>&1
```


# Sources
[Ubuntu wiki](https://wiki.ubuntuusers.de/Citrix_Receiver_13/)
