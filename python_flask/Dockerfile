FROM python:latest
RUN pip install flask
WORKDIR /app
COPY app.py .
EXPOSE 5000
HEALTHCHECK --interval=1m --timeout=30s \
            --start-period=30s --retries=3 \    
           CMD curl -f http://localhost:5000/health || exit 1
ENTRYPOINT ["python", "app.py"]