FROM rocker/binder:4.1.0
LABEL maintainer='Jeanette Clark <jclark@nceas.ucsb.edu>'
## Declares build arguments
ARG NB_USER
ARG NB_UID

COPY --chown=${NB_USER} . ${HOME}

USER ${NB_USER}

RUN wget https://github.com/jeanetteclark/mypaper2/raw/main/DESCRIPTION
RUN R --vanilla -s -e "options(repos = list(CRAN = 'http://cran.rstudio.com'));  install.packages('renv'); renv::restore()"

RUN rm DESCRIPTION.1; exit 0
