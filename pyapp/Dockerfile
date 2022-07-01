# set base image (host OS)
FROM python:2.7-slim
ENV http_proxy http://host.docker.internal:3128
ENV https_proxy http://host.docker.internal:3128
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
//RUN apt-get install -y python3 python3-pip
EXPOSE 5000
CMD ["python3", "app.py"]
