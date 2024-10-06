FROM condaforge/miniforge3:latest

ARG DEBIAN_FRONTEND=noninteractive
ENV TZ=Europe/Helsinki

RUN apt-get update && apt upgrade -y

RUN mamba install -y ipykernel pysal polars jupyterlab seaborn plotly duckdb sqlalchemy 

RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 8888
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]