FROM docker.repository.cloudera.com/cdsw/ml-runtime-jupyterlab-python3.6-standard:2021.09.1-b5

# Install telnet in the new image
RUN apt-get update && apt-get install -y --no-install-recommends telnet && apt-get clean && rm -rf /var/lib/apt/lists/*


# Upgrade packages in the base image
RUN apt-get update && apt-get upgrade -y && apt-get clean && rm -rf /var/lib/apt/lists/*


# Install the python package sklearn
RUN pip3 install --no-cache-dir jupyterlab-git

ENV ML_RUNTIME_EDITOR="JupyterLab" \
    ML_RUNTIME_EDITION="Standard"       \
    ML_RUNTIME_SHORT_VERSION="2021.09" \
    ML_RUNTIME_MAINTENANCE_VERSION="3" \
    ML_RUNTIME_FULL_VERSION="2021.09.3" \
    ML_RUNTIME_DESCRIPTION="Testing Jupyter" \
    ML_RUNTIME_KERNEL="Python 3.6"

LABEL com.cloudera.ml.runtime.editor=$ML_RUNTIME_EDITOR \
      com.cloudera.ml.runtime.edition=$ML_RUNTIME_EDITION \
      com.cloudera.ml.runtime.full-version=$ML_RUNTIME_FULL_VERSION \
      com.cloudera.ml.runtime.short-version=$ML_RUNTIME_SHORT_VERSION \
      com.cloudera.ml.runtime.maintenance-version=$ML_RUNTIME_MAINTENANCE_VERSION \
      com.cloudera.ml.runtime.description=$ML_RUNTIME_DESCRIPTION \
      com.cloudera.ml.runtime.kernel=$ML_RUNTIME_KERNEL
