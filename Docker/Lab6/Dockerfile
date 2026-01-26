FROM python:3.15-rc-slim
WORKDIR /app
COPY ./Docker-3 .
RUN pip install flask 
ENV APP-MODE=production
ENV APP-REGION=canada-west
EXPOSE 8080
CMD ["python" , "app.py"] 
