FROM solr:7.2.1-alpine

# Enviroment
ENV SOLR_CORE mir

# User
USER $SOLR_USER

# Create Directories
RUN mkdir -p /opt/solr/server/solr/$SOLR_CORE/conf /opt/solr/server/solr/$SOLR_CORE/data

WORKDIR /opt/solr/server/solr/$SOLR_CORE
COPY mir ./ 

# Giving ownership to Solr
USER root
RUN chown -R $SOLR_USER:$SOLR_USER . 
USER $SOLR_USER
