# Use an official Python runtime as a parent image
FROM python:2.7-slim

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
# ADD . /app
ADD ./requirements.txt /app/requirements.txt

# COPY docker_run file
COPY ./docker_run.sh /run/docker_run.sh
RUN sed -i 's/\r//' /run/docker_run.sh
RUN chmod +x /run/docker_run.sh

# RUN add 
# RUN apt-get update && apt-get install libffi-dev libpq-dev python-dev python-psycopg2 -y

# Install any needed packages specified in requirements.txt
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Make port 80 available to the world outside this container
# EXPOSE 80

# Define environment variable
ENV NAME DonAvto

# Run app.py when the container launches
# CMD ["python", "run.py"]
# CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:80", "run_gunicorn:app"] 
# gunicorn -w 4 -b 0.0.0.0:80 run_gunicorn:app
# ENTRYPOINT ["sh", "/run/docker_run.sh"]