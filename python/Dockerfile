 
FROM python:3.7

WORKDIR /data

RUN pip install jupyter -U && pip install jupyterlab

EXPOSE 5000 8888

ENTRYPOINT ["jupyter", "lab","--ip=0.0.0.0","--allow-root"]
