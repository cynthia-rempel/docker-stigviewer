ROM registry.hub.docker.com/library/centos:centos7.6.1810

RUN rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7 \
  && yum -y update

RUN yum -y install wget unzip openscap scap-security-guide

RUN yum -y install java-1.8.0-openjdk.x86_64

RUN wget https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/unclass-STIGViewer_2-9.zip \
  && unzip unclass-STIGViewer_2-9.zip \
  && rm -rf unclass-STIGViewer_2-9.zip

RUN wget https://download-ib01.fedoraproject.org/pub/fedora/linux/updates/29/Everything/x86_64/Packages/o/openjfx-8.0.202-8.b07.fc29.x86_64.rpm \
  && yum -y localinstall openjfx-8.0.202-8.b07.fc29.x86_64.rpm

RUN cp -r /usr/lib/jvm/openjfx/rt/lib/* /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.222.b10-0.el7_6.x86_64/jre/lib/

RUN yum -y install mesa-dri-drivers
RUN wget https://chriswhocodes.com/downloads/openjfx-8-sdk-overlay-linux-amd64.zip \
  && mkdir openjfx-8-sdk-overlay-linux-amd64 \
  && unzip openjfx-8-sdk-overlay-linux-amd64.zip -d openjfx-8-sdk-overlay-linux-amd64 \
  && cp openjfx-8-sdk-overlay-linux-amd64/jre/lib/amd64/libjfxwebkit.so \
        /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.222.b10-0.el7_6.x86_64/jre/lib/amd64/
