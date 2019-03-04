ARG repository
FROM ${repository}:10.0-devel-centos6
LABEL maintainer "NVIDIA CORPORATION <cudatools@nvidia.com>"

ENV CUDNN_VERSION 7.5.0.56
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=701097882cb745d4683bb7ff6c33b8a35c7c81be31bac78f05bad130e7e0b781 && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.5.0/cudnn-10.0-linux-x64-v7.5.0.56.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-10.0-linux-x64-v7.5.0.56.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-10.0-linux-x64-v7.5.0.56.tgz -C /usr/local && \
    rm cudnn-10.0-linux-x64-v7.5.0.56.tgz && \
    ldconfig
