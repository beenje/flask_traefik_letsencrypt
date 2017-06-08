FROM continuumio/miniconda3:latest

# Add conda-forge to get uwsgi
RUN conda config --add channels conda-forge && \
    conda create -y -n flask python=3 flask=0.12 uwsgi

# Create a flask user to avoid running uwsgi as root
RUN useradd -r flask

COPY app.py /app/app.py
RUN chown -R flask /app

USER flask

# activate the flask environment
ENV PATH /opt/conda/envs/flask/bin:$PATH
WORKDIR /app

EXPOSE 5000

CMD ["uwsgi", "--http-socket", "0.0.0.0:5000", "--wsgi-file", "app.py", "--callable", "app"]
