FROM python:3.5

RUN apt-get update \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


RUN groupadd -g 799 kk5243 && \
    useradd -r -u 999 -g kk5243 kk5243

# Set up a working folder and install the pre-reqs
WORKDIR /app

RUN pip install Flask

RUN pip install requests

USER root

COPY --chown=kk5243:kk5243 . .

CMD [ "python", "./AS.py" ]
