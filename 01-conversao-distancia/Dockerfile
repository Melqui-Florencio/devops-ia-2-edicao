FROM python
WORKDIR /app
COPY requirements.txt ./requirements.txt
RUN pip install -r requirements.txt
RUN adduser -u 5678 --disabled-password --gecos "" appuser && chown -R appuser /app
USER appuser
EXPOSE 8000
COPY . .
CMD ["gunicorn", "-w", "4", "b",  "0.0.0.0:8000", "main:app"]
