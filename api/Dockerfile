# Use the official Python 3.11.5 image as the base image
FROM python:3.11.5

# Set the working directory to /app/api
WORKDIR /app/api

# Copy the requirements.txt file from the api directory to the /tmp directory in the container
COPY api/requirements.txt /tmp/requirements.txt

# Install the Python dependencies specified in requirements.txt
RUN python -m pip install --no-cache-dir --timeout 300000 -r /tmp/requirements.txt

# Copy the Models directory into the container
COPY api/Models /api/Models

# Copy the entire api directory to the /app/api directory in the container
COPY api /app/api

# Expose port 80 for the application
EXPOSE 80

# Command to run the application using Uvicorn, specifying the host and port
CMD ["uvicorn", "api:app", "--host", "0.0.0.0", "--port", "80"]