# Simple Webserver in Node.js to demonstrate testing releases with Docker

### You can run the sample like this

`docker run -p 3000:3000 -e github='https://github.com/pmcdowell-okta/Simple-node-webserver.git' -it oktaadmin/dockertest`

This what the **JB Dockerfile** contains, nothing special.

```
FROM oktaadmin/awscli

RUN echo "#!/bin/bash\n" > /startscript.sh
RUN echo "mkdir github\n" >> /startscript.sh
RUN echo "cd github\n" >> /startscript.sh
RUN echo "git clone \$github\n" >> /startscript.sh
RUN echo "cd *\n" >> /startscript.sh
RUN echo "make dockertest\n" >> /startscript.sh

RUN chmod +x /startscript.sh

CMD /startscript.sh

```
