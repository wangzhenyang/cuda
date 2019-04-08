ARG IMAGE_NAME
FROM ${IMAGE_NAME}:9.0-devel-centos6
LABEL maintainer "NVIDIA CORPORATION <cudatools@nvidia.com>"

ENV CUDNN_VERSION 7.5.0.56
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=ee0ecd3cc30b9bf5ec875eac3ed375d3996bcb0ed5d2551716e4884b3ea5ce8c && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.5.0/cudnn-9.0-linux-x64-v7.5.0.56.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-9.0-linux-x64-v7.5.0.56.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-9.0-linux-x64-v7.5.0.56.tgz -C /usr/local && \
    rm cudnn-9.0-linux-x64-v7.5.0.56.tgz && \
    ldconfig
