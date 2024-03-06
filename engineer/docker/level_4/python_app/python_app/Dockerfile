FROM python:3.12.2-alpine3.18
WORKDIR /app
RUN addgroup -S appgroup && adduser -S appuser -G appgroup  && \
    chown appuser /app
COPY src/requirements.txt   /app
RUN pip install -r requirements.txt
COPY src/server.py /app
USER appuser
EXPOSE 8085
CMD ["python", "server.py"]
