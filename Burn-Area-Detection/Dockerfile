FROM python:3.9

# 
WORKDIR /code

# 
COPY ./requirements.txt /code/requirements.txt

# 
RUN pip install --upgrade pip
RUN pip install --no-cache-dir --upgrade -r /code/requirements.txt
RUN pip install tensorflow==2.5.0
RUN pip install --upgrade pydantic dataclasses
RUN pip install matplotlib==3.4.3

#cv2
RUN apt-get update && apt-get install ffmpeg libsm6 libxext6  -y

# 
COPY ./app /code/app

# 
ENV PYTHONPATH /code
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "80"]