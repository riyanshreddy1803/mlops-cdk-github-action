FROM amazon/aws-lambda-python:latest

# Install required packages using 'yum' for the correct base image
RUN yum install -y python3 python3-devel gcc && \
    yum clean all

# Copies requirements.txt file into the container
COPY requirements.txt ./

# Installs dependencies found in your requirements.txt file
RUN pip3 install --no-cache-dir -r requirements.txt

# Be sure to copy over the function itself!
# Goes last to take advantage of Docker caching.
COPY index.py ./

# Points to the handler function of your lambda function
CMD ["index.handler"]
