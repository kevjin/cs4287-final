# Generated Dockerfile, do not modify directly!
# Modify `dockergen.yaml` and run
#   `python images/dockergen.py` in the root directory.
FROM kevjin/runlang_base:latest
SHELL ["/bin/bash", "-c"]

COPY run_lang/requirements.txt /tmp/requirements.txt
RUN pip3 install --requirement /tmp/requirements.txt

# Pre-install
RUN curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
RUN apt-get install -y nodejs

# Package install
RUN npm install lodash@4.17.20
RUN npm install axios@0.21.0
RUN npm install rxjs@6.6.3

# Post-install
RUN echo 0

# Service setup.
COPY run_lang /run_lang
COPY start_run_lang.sh /start_run_lang.sh
COPY images/javascript/packages /packages

ENV RUN_LANG_WHICH="javascript"
ENV RUN_LANG_WHICH_DESCRIPTION="node 12"

WORKDIR /

CMD ["./start_run_lang.sh"]
