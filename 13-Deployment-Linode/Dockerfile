FROM python:3.9.0

RUN adduser --disabled-password --gecos '' api-user

WORKDIR /opt/flaskblog

ENV SECRET_KEY '5791628bb0b13ce0c676dfde280ba245'
ENV SQLALCHEMY_DATABASE_URI 'sqlite:///site.db'

ENV FLASK_APP run.py

ADD ./ /opt/flaskblog/
RUN pip install --upgrade pip
RUN pip install -r /opt/flaskblog/requirements.txt

RUN chmod +x /opt/flaskblog/run.sh
RUN chown -R api-user:api-user ./

USER api-user

EXPOSE 5000

CMD ["bash", "./run.sh"]






