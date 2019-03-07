ARG IMAGE_NAME
FROM ${IMAGE_NAME}:10.1-runtime-centos6
LABEL maintainer "NVIDIA CORPORATION <cudatools@nvidia.com>"

ENV CUDNN_VERSION 7.5.0.56
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=c31697d6b71afe62838ad2e57da3c3c9419c4e9f5635d14b683ebe63f904fbc8 && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.5.0/cudnn-10.1-linux-x64-v7.5.0.56.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-10.1-linux-x64-v7.5.0.56.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-10.1-linux-x64-v7.5.0.56.tgz -C /usr/local --wildcards 'cuda/lib64/libcudnn.so.*' && \
    rm cudnn-10.1-linux-x64-v7.5.0.56.tgz && \
    ldconfig
