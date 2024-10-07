FROM jupyter/minimal-notebook

USER root

COPY  /jupyter/intersystems_irispython-3.2.0-py3-none-any.whl /
RUN chmod 777 /intersystems_irispython-3.2.0-py3-none-any.whl

COPY  /jupyter/requirements.txt /
RUN chmod 777 /requirements.txt

RUN pip install /*.whl

RUN pip install -r /requirements.txt