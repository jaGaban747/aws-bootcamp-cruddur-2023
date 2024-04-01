FROM python:3.10-slim-buster

# Inside container
# make a new folder inside a container
WORKDIR /backend-flask

# Outside container -> Inside container
# This contains the libraries we want to install to run the app
COPY requirements.txt requirements.txt

# Inside container
# Install the python libraries used for the app
RUN pip3 install -r requirements.txt

# "Period(.)" means everything in the current directory
# firstperiod (.) means everything in /backend-flask (outside the container)
# secondperiod (.) means everything in /backend-flask(inside the container)
COPY . .

# Set environment variables( envars)
# Inside the container and will remain set there when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}
# CMD (command)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]