FROM ubuntu:20.04

RUN apt-get update
RUN apt-get -y install openjdk-17-jdk-headless
RUN apt-get -y install git
RUN apt-get -y install less vim
RUN apt-get -y install wget
RUN wget https://downloads.lightbend.com/scala/2.13.8/scala-2.13.8.deb && apt-get -y install ./scala-2.13.8.deb
RUN apt-get install apt-transport-https curl gnupg -yqq
RUN echo "deb https://repo.scala-sbt.org/scalasbt/debian all main" | tee /etc/apt/sources.list.d/sbt.list
RUN echo "deb https://repo.scala-sbt.org/scalasbt/debian /" | tee /etc/apt/sources.list.d/sbt_old.list
RUN curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | gpg --no-default-keyring --keyring gnupg-ring:/etc/apt/trusted.gpg.d/scalasbt-release.gpg --import
RUN chmod 644 /etc/apt/trusted.gpg.d/scalasbt-release.gpg
RUN apt-get update
RUN apt-get install sbt

CMD ["/bin/bash"]

