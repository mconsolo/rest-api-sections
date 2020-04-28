#
# Section 3 app
#

# Pull base image.
FROM python:3.7.3-slim

# Get some custom packages
#RUN apt-get update && apt-get install -y \
#    build-essential \
#    make \
#    gcc \
#    python3-dev

## make a local directory
#RUN mkdir /opt/store

# set "store" as the working directory from which CMD, RUN, ADD references
WORKDIR /opt/store

# now copy all the files in this directory to /code
ADD . .

# Convert ADD command to volume so you can change app file on the  fly.
#VOLUME . /opt/store

# pip install the local requirements.txt
RUN pip install -r requirements.txt

# Listen to port 5000 at runtime
EXPOSE 5000

# start the app server
CMD python app.py

# build & run container
# docker build -t python_api:section3app .
# docker run --name="section3-app" -d -p 5000:5000 python:section3app
# docker exec -it <container-name>
# docker run --name="section3-app" --rm -p 5000:5000 <image-name>   # run the container then delete it after shutting it down.