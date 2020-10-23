FROM alpine
RUN apk add --no-cache bash
RUN apk add --no-cache python3
RUN python3 -m ensurepip
RUN pip3 install --no-cache-dir --upgrade pip setuptools
CMD [ "/bin/bash" ]