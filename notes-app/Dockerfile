FROM python:3.11

WORKDIR /app

COPY requirements.txt /app
RUN pip install -r requirements.txt
# Install the OpenTelemetry instrumentation matching the libraries above (Django, etc.)
COPY . /app

EXPOSE 8000

# opentelemetry-instrument wraps the app: traces, metrics and logs with zero code changes
# CMD python /app/manage.py 0.0.0.0:8000
CMD ["python", "/app/manage.py", "runserver", "0.0.0.0:8000"]
