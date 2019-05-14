ARG IMAGE_NAME
FROM ${IMAGE_NAME}:9.0-runtime-centos7
LABEL maintainer "NVIDIA CORPORATION <cudatools@nvidia.com>"

ENV CUDNN_VERSION 7.5.1.10
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=1abe08839dcb59a3a7293c85f642bf0dd2486e377d0fbca1b0311f38e183251a && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.5.1/cudnn-9.0-linux-x64-v7.5.1.10.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-9.0-linux-x64-v7.5.1.10.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-9.0-linux-x64-v7.5.1.10.tgz -C /usr/local --wildcards 'cuda/lib64/libcudnn.so.*' && \
    rm cudnn-9.0-linux-x64-v7.5.1.10.tgz && \
    ldconfig
