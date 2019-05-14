ARG IMAGE_NAME
FROM ${IMAGE_NAME}:9.2-runtime-centos6
LABEL maintainer "NVIDIA CORPORATION <cudatools@nvidia.com>"

ENV CUDNN_VERSION 7.5.1.10
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=e840d29ce5f0c068911966e62128397c6a9bb5e2ea9c66394a592c3b61e770a5 && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.5.1/cudnn-9.2-linux-x64-v7.5.1.10.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-9.2-linux-x64-v7.5.1.10.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-9.2-linux-x64-v7.5.1.10.tgz -C /usr/local --wildcards 'cuda/lib64/libcudnn.so.*' && \
    rm cudnn-9.2-linux-x64-v7.5.1.10.tgz && \
    ldconfig
