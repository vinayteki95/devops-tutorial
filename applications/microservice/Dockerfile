FROM 1k3tv1nay/alpine-python3:latest
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 80
# CMD [ "python3", "server.py" ]