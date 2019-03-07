ARG IMAGE_NAME
FROM ${IMAGE_NAME}:9.2-runtime-centos6
LABEL maintainer "NVIDIA CORPORATION <cudatools@nvidia.com>"

ENV CUDNN_VERSION 7.4.2.24
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=19565be5dba39097d59f99227fd65cd2f3a3be9e4249500f772d4b14c7806371 && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.4.2/cudnn-9.2-linux-x64-v7.4.2.24.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-9.2-linux-x64-v7.4.2.24.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-9.2-linux-x64-v7.4.2.24.tgz -C /usr/local --wildcards 'cuda/lib64/libcudnn.so.*' && \
    rm cudnn-9.2-linux-x64-v7.4.2.24.tgz && \
    ldconfig
