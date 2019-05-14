ARG IMAGE_NAME
FROM ${IMAGE_NAME}:10.1-devel-centos6
LABEL maintainer "NVIDIA CORPORATION <cudatools@nvidia.com>"

ENV CUDNN_VERSION 7.5.1.10
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=2c833f43c9147d9a25a20947a4c5a5f5c33b2443240fd767f63b330c482e68e0 && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.5.1/cudnn-10.1-linux-x64-v7.5.1.10.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-10.1-linux-x64-v7.5.1.10.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-10.1-linux-x64-v7.5.1.10.tgz -C /usr/local && \
    rm cudnn-10.1-linux-x64-v7.5.1.10.tgz && \
    ldconfig
