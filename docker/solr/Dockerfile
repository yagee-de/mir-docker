FROM solr:7.2.1-alpine

# Enviroment
ENV SOLR_CORE mir

# User
USER $SOLR_USER

# Create Directories
RUN mkdir -p /opt/solr/server/solr/$SOLR_CORE/conf /opt/solr/server/solr/$SOLR_CORE/data

WORKDIR /opt/solr/server/solr/$SOLR_CORE
COPY --chown=8983:8983 mir ./ 

# Bugfix for Solr <7.3.0
WORKDIR /opt/solr/contrib/extraction/lib
RUN rm -rf \
poi-scratchpad-3.17-beta1.jar \
poi-ooxml-schemas-3.17-beta1.jar \
poi-ooxml-3.17-beta1.jar \
poi-3.17-beta1.jar \
tika-core-1.16.jar \
tika-xmp-1.16.jar \
tika-java7-1.16.jar \
tika-parsers-1.16.jar

ADD --chown=8983:8983 http://central.maven.org/maven2/org/apache/poi/poi/3.17/poi-3.17.jar \
http://central.maven.org/maven2/org/apache/poi/poi-ooxml/3.17/poi-ooxml-3.17.jar \
http://central.maven.org/maven2/org/apache/poi/poi-ooxml-schemas/3.17/poi-ooxml-schemas-3.17.jar \
http://central.maven.org/maven2/org/apache/poi/poi-scratchpad/3.17/poi-scratchpad-3.17.jar \
http://central.maven.org/maven2/org/apache/tika/tika-core/1.17/tika-core-1.17.jar \
http://central.maven.org/maven2/org/apache/tika/tika-xmp/1.17/tika-xmp-1.17.jar \
http://central.maven.org/maven2/org/apache/tika/tika-java7/1.17/tika-java7-1.17.jar \
http://central.maven.org/maven2/org/apache/tika/tika-parsers/1.17/tika-parsers-1.17.jar \
./

