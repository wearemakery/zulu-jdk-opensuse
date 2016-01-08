FROM opensuse

MAINTAINER Gyula Voros <gyulavoros87@gmail.com>

ENV ZULU_VERSION zulu1.8.0_66-8.11.0.1-x86lx64

ENV JAVA_HOME /usr/lib/jvm/zulu-8/
ENV JRE ${JAVA_HOME}/jre
ENV JAVA_OPTS=-Djava.awt.headless=true
ENV PATH=${PATH}:${JRE}/bin:${JAVA_HOME}/bin

RUN zypper -n in wget \
  && wget -q -P /tmp/ --referer=http://www.azulsystems.com/zuludoc http://cdn.azulsystems.com/zulu/bin/$ZULU_VERSION.rpm \
  && rpm -ih --nodeps /tmp/$ZULU_VERSION.rpm \
  && rm -rf /tmp/$ZULU_VERSION.rpm \
  && cd ${JAVA_HOME} \
  && rm -rf *.zip demo man sample \
  && zypper -n rm wget \
  && zypper clean
