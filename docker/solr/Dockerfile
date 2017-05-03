FROM solr:6.5-alpine

# Enviroment
ENV SOLR_CORE mir

# User
USER $SOLR_USER

# Create Directories
RUN mkdir -p /opt/solr/server/solr/$SOLR_CORE/conf /opt/solr/server/solr/$SOLR_CORE/data

WORKDIR /opt/solr/server/solr/$SOLR_CORE/conf
RUN find ../../configsets/basic_configs/conf -maxdepth 1 ! -name managed-schema -exec ln -sfn {} ./ +

# Adding Files
COPY \
./solrconfig.xml \
./schema.xml \
./mapping.txt \
./

# Create Core.properties
COPY core.properties ../
#RUN echo name=$SOLR_CORE > ../core.properties

# Giving ownership to Solr
USER root
RUN chown $SOLR_USER:$SOLR_USER solrconfig.xml schema.xml mapping.txt ../core.properties
USER $SOLR_USER
