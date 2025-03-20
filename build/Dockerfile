FROM python:3.9-slim-buster

LABEL Name="Python Flask Demo App" Version=1.4.2
LABEL org.opencontainers.image.source = "https://github.com/benc-uk/python-demoapp"

WORKDIR /app

# Pastikan file requirements.txt ada
COPY src/requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy file aplikasi
COPY src/run.py .
COPY src/app ./app

# Expose port aplikasi
EXPOSE 5000

CMD ["gunicorn", "-b", "0.0.0.0:5000", "run:app"]
