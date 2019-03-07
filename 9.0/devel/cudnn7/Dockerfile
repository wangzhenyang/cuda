ARG IMAGE_NAME
FROM ${IMAGE_NAME}:9.0-devel-centos7
LABEL maintainer "NVIDIA CORPORATION <cudatools@nvidia.com>"

ENV CUDNN_VERSION 7.4.2.24
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=e3e72e9e2bf4c5e4cdd467aa6b824effc4566d230a2cda4153ad894d7d15cf73 && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.4.2/cudnn-9.0-linux-x64-v7.4.2.24.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-9.0-linux-x64-v7.4.2.24.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-9.0-linux-x64-v7.4.2.24.tgz -C /usr/local && \
    rm cudnn-9.0-linux-x64-v7.4.2.24.tgz && \
    ldconfig
