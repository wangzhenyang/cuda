ARG repository
FROM ${repository}:10.0-devel-centos6
LABEL maintainer "NVIDIA CORPORATION <cudatools@nvidia.com>"

ENV CUDNN_VERSION 7.4.2.24
LABEL com.nvidia.cudnn.version="${CUDNN_VERSION}"

# cuDNN license: https://developer.nvidia.com/cudnn/license_agreement
RUN CUDNN_DOWNLOAD_SUM=4e15a323f2edffa928b4574f696fc0e449a32e6bc35c9ccb03a47af26c2de3fa && \
    curl -fsSL http://developer.download.nvidia.com/compute/redist/cudnn/v7.4.2/cudnn-10.0-linux-x64-v7.4.2.24.tgz -O && \
    echo "$CUDNN_DOWNLOAD_SUM  cudnn-10.0-linux-x64-v7.4.2.24.tgz" | sha256sum -c - && \
    tar --no-same-owner -xzf cudnn-10.0-linux-x64-v7.4.2.24.tgz -C /usr/local && \
    rm cudnn-10.0-linux-x64-v7.4.2.24.tgz && \
    ldconfig
