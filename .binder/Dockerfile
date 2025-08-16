FROM ghcr.io/binder-examples/python-minimal:latest

USER root
RUN apt-get update && apt-get install -y \
    ffmpeg \
    texlive-base \
    texlive-fonts-recommended \
    texlive-fonts-extra \
    texlive-latex-base \
    texlive-latex-recommended \
    texlive-latex-extra \
    && rm -rf /var/lib/apt/lists/*

USER ${NB_USER}
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY start /home/${NB_USER}/start
RUN chmod +x /home/${NB_USER}/start

CMD ["/home/${NB_USER}/start"]
