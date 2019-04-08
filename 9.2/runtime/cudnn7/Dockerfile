ARG IMAGE_NAME
FROM ${IMAGE_NAME}:9.2-runtime-centos7
LABEL maintainer "NVIDIA CORPORATION <cudatools@nvidia.com>"

ENV CUDNN_VERSION 7.5.0.56
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=2a04fd5ed5b8d32e2401c85a1a38f3cfd6da662c31bd26e80bea25469e48a675 && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.5.0/cudnn-9.2-linux-x64-v7.5.0.56.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-9.2-linux-x64-v7.5.0.56.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-9.2-linux-x64-v7.5.0.56.tgz -C /usr/local --wildcards 'cuda/lib64/libcudnn.so.*' && \
    rm cudnn-9.2-linux-x64-v7.5.0.56.tgz && \
    ldconfig
