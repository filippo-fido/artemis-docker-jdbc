# Operazioni effettuate per la creazione di questa directory

    git clone --depth 1 https://github.com/apache/activemq-artemis.git
    cd activemq-artemis/artemis-docker/
    ./prepare-docker.sh --from-release --artemis-version 2.16.0
    cd _TMP_/artemis/2.16.0
    wget https://downloads.mariadb.com/Connectors/java/connector-java-2.4.4/mariadb-java-client-2.4.4.jar -O lib/mariadb-java-client-2.4.4.jar
    docker build -f ./docker/Dockerfile-adoptopenjdk-11 -t artemis-adoptopenjdk-11 .

# Modifica all'entrypoint del container 

È modificato il file docker/docker-run.s in modo da usare il file di configurazione derivante dal configmap di k8s, e non la versione autogenerata.
