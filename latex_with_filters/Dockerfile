ARG base_image=

FROM $base_image

ARG pandoc_version
ARG crossref_release

# install utils
RUN apk add xz make \
    # install python
        python3 \
        py3-psutil \
    # get crossref
    && wget -O- "https://github.com/lierdakil/pandoc-crossref/releases/download/"${crossref_release}"/pandoc-crossref-Linux-"${pandoc_version}".tar.xz" | tar xJ -C /usr/bin/ pandoc-crossref \
    # install pip
    && python3 -m pip install --upgrade pip \
    # install pandoc-*nos filters
    && pip3 install \
        pandoc-eqnos \
        pandoc-fignos \
        pandoc-secnos \
        pandoc-tablenos \
    # required tex packages
    && `which tlmgr` update --self \
    && `which tlmgr` install cleveref

LABEL maintainer='Jaromir Radek <jradek@yandex.com>'
LABEL org.pandoc.maintainer='Albert Krewinkel <albert+pandoc@zeitkraut.de>'
LABEL org.pandoc.author "John MacFarlane"
LABEL org.pandoc.version "${pandoc_version}"

WORKDIR /data
