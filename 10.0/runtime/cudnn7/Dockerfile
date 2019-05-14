ARG IMAGE_NAME
FROM ${IMAGE_NAME}:10.0-runtime-centos7
LABEL maintainer "NVIDIA CORPORATION <cudatools@nvidia.com>"

ENV CUDNN_VERSION 7.5.1.10
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=c0a4ec438920aa581dd567117b9c316745b4a451ac739b1e04939a3d8b229985 && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.5.1/cudnn-10.0-linux-x64-v7.5.1.10.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-10.0-linux-x64-v7.5.1.10.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-10.0-linux-x64-v7.5.1.10.tgz -C /usr/local --wildcards 'cuda/lib64/libcudnn.so.*' && \
    rm cudnn-10.0-linux-x64-v7.5.1.10.tgz && \
    ldconfig
