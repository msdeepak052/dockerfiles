# Use a lightweight Python image
FROM python:3.9-alpine

# Set the working directory
WORKDIR /app

# Copy requirements.txt and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application files
COPY . .

# Expose Flask's default port
EXPOSE 5000

# Run the Flask app
CMD ["python", "app.py"]
