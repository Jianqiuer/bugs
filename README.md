# bugs


## 1. Unsupported gpu architecture 'compute_86'

looking for thie shell and match the highest vision of  yout CUDA VISION and TORCH_CUDA_ARCH_LIST



TORCH_CUDA_ARCH_LIST="3.7;5.0;6.0;7.0"
case ${CUDA_VERSION} in
    11.[12])
        TORCH_CUDA_ARCH_LIST="${TORCH_CUDA_ARCH_LIST};7.5;8.0;8.6"
        EXTRA_CAFFE2_CMAKE_FLAGS+=("-DATEN_NO_TEST=ON")
        ;;
    11.0)
        TORCH_CUDA_ARCH_LIST="${TORCH_CUDA_ARCH_LIST};7.5;8.0"
        EXTRA_CAFFE2_CMAKE_FLAGS+=("-DATEN_NO_TEST=ON")
        ;;
    10.*)
        TORCH_CUDA_ARCH_LIST="${TORCH_CUDA_ARCH_LIST}"
        EXTRA_CAFFE2_CMAKE_FLAGS+=("-DATEN_NO_TEST=ON")
        ;;
    9.*)
        TORCH_CUDA_ARCH_LIST="${TORCH_CUDA_ARCH_LIST}"
        ;;
    *)
        echo "unknown cuda version $CUDA_VERSION"
        exit 1
        ;;
esac

###  then 
export TORCH_CUDA_ARCH_LIST="8.0"
