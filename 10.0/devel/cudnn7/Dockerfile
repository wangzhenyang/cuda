ARG repository
FROM ${repository}:10.0-devel-centos7
LABEL maintainer "NVIDIA CORPORATION <cudatools@nvidia.com>"

ENV CUDNN_VERSION 7.4.2.24
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=2edfc86a02b50d17e88c478955a332e6a1e8174e7e53a3458b4ea51faf02daa3 && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.3.1/cudnn-10.0-linux-x64-v7.4.2.24.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-10.0-linux-x64-v7.4.2.24.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-10.0-linux-x64-v7.4.2.24.tgz -C /usr/local && \
    rm cudnn-10.0-linux-x64-v7.4.2.24.tgz && \
    ldconfig
