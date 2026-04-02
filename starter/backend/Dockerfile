FROM python:3.10-slim

ENV FLASK_RUN_HOST=0.0.0.0

WORKDIR /app

# ✅ Install system dependencies (THIS FIXES YOUR ERROR)
RUN apt-get update && apt-get install -y \
    build-essential \
    gcc \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt /app

RUN pip install --upgrade pip && \
    pip install -r requirements.txt

COPY . /app

CMD ["uwsgi", "--http", ":5000", "--master", "--enable-threads", "-s", "/var/www/app/app.sock", "--manage-script-name", "--mount", "/=app:app"]


IQoJb3JpZ2luX2VjEFwaCXVzLXdlc3QtMiJIMEYCIQDqZ1R33Tiv0NfojxbU53asRpEIr4F7guayB7/s8KmDmwIhAPMB/FH4adR8TWpGQwSwRCpgLciOnigunKKhGwGsNlubKr4CCCUQAhoMNzI2NDU5MDM1NTMzIgz4Q5aewKVnpopWjqwqmwIsSyLvLt74BpaS2lOWtN33zAWabd5C/xEXLrKLGo1gphxWhyrJV/kWDi40BlQyXD7woO3bUgqOd0xpEiwedJRzlJ0qCrng942ucZjpNDvdUNuB7A4ZV2L++4jRy0PuZUIrUO9GG020JrEBfczBXeu8WBEdrVg1AoJFU/MQ7AatzvHffDBvuLSRS8jMgpD3wP7MsDmN52nMbZwxZeTPM3oUsSdoFjLqCdv3pk45oxi4/f9Y0obj7f1vBCFZ7YBvnp7mGiguxHB0enMOCumvvb5wasSkp5CRLSRIZx5gC4xvXvabvl9OApjUnJY2/Xixf3wkvxYaZbYqA3cSQPsBbCRpA57C/dXKdbMCM7uPwRsYDSTDI6f9OhxnwgV8MMvDqc4GOpwByitL1KvFprG3R9g18bkAXfjZKVYmST2e9q+L4n5WYGodZPgwJDlwqh6ClDC8WQhfN7LHcR9m2e3Pv8pAZbtPn1MOORSSLO2d9w+lvD21VBk2WedmlE1yppWy6U1CSqIQ/xaJljBc6OE23RFodF1AghWJgA1p+gDPJRfMt5pH9gpkoPCpvfnGBpQS9wESgadMEv1pg6zXp/5QrTa9