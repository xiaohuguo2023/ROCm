# Release Notes
<!-- Do not edit this file! This file is autogenerated with -->
<!--   tools/autotag/tag_script.py                          -->

<!-- Disable lints since this is an auto-generated file.    -->
<!-- markdownlint-disable blanks-around-headers             -->
<!-- markdownlint-disable no-duplicate-header               -->
<!-- markdownlint-disable no-blanks-blockquote              -->
<!-- markdownlint-disable ul-indent                         -->
<!-- markdownlint-disable no-trailing-spaces                -->

<!-- spellcheck-disable -->

Welcome to the release notes for the ROCm platform.

-------------------

## ROCm 5.7.1
<!-- markdownlint-disable first-line-h1 -->
<!-- markdownlint-disable no-duplicate-header -->

### What's New in This Release

### ROCm Libraries

#### rocBLAS
A new functionality rocblas-gemm-tune and an environment variable ROCBLAS_TENSILE_GEMM_OVERRIDE_PATH are added to rocBLAS in the ROCm 5.7.1 release.

*rocblas-gemm-tune* is used to find the best-performing GEMM kernel for each GEMM problem set. It has a command line interface, which mimics the --yaml input used by rocblas-bench. To generate the expected --yaml input, profile logging can be used, by setting the environment variable ROCBLAS_LAYER4.

For more information on rocBLAS logging, see Logging in rocBLAS, in the [API Reference Guide](https://rocm.docs.amd.com/projects/rocBLAS/en/docs-5.7.1/API_Reference_Guide.html#logging-in-rocblas).

An example input file: Expected output (note selected GEMM idx may differ): Where the far right values (solution_index) are the indices of the best-performing kernels for those GEMMs in the rocBLAS kernel library. These indices can be directly used in future GEMM calls. See rocBLAS/samples/example_user_driven_tuning.cpp for sample code of directly using kernels via their indices.

If the output is stored in a file, the results can be used to override default kernel selection with the kernels found, by setting the environment variable ROCBLAS_TENSILE_GEMM_OVERRIDE_PATH, where points to the stored file.

For more details, refer to the [rocBLAS Programmer's Guide.](https://rocm.docs.amd.com/projects/rocBLAS/en/latest/Programmers_Guide.html#rocblas-gemm-tune)

#### HIP 5.7.1 (for ROCm 5.7.1)

ROCm 5.7.1 is a point release with several bug fixes in the HIP runtime.

### Fixed defects
The *hipPointerGetAttributes* API returns the correct HIP memory type as *hipMemoryTypeManaged* for managed memory.

### Library Changes in ROCM 5.7.1

| Library | Version |
|---------|---------|
| hipBLAS | [1.1.0](https://github.com/ROCmSoftwarePlatform/hipBLAS/releases/tag/rocm-5.7.1) |
| hipCUB | [2.13.1](https://github.com/ROCmSoftwarePlatform/hipCUB/releases/tag/rocm-5.7.1) |
| hipFFT | [1.0.12](https://github.com/ROCmSoftwarePlatform/hipFFT/releases/tag/rocm-5.7.1) |
| hipSOLVER | 1.8.1 ⇒ [1.8.2](https://github.com/ROCmSoftwarePlatform/hipSOLVER/releases/tag/rocm-5.7.1) |
| hipSPARSE | [2.3.8](https://github.com/ROCmSoftwarePlatform/hipSPARSE/releases/tag/rocm-5.7.1) |
| MIOpen | [2.19.0](https://github.com/ROCmSoftwarePlatform/MIOpen/releases/tag/rocm-5.7.1) |
| rocALUTION | [2.1.11](https://github.com/ROCmSoftwarePlatform/rocALUTION/releases/tag/rocm-5.7.1) |
| rocBLAS | [3.1.0](https://github.com/ROCmSoftwarePlatform/rocBLAS/releases/tag/rocm-5.7.1) |
| rocFFT | [1.0.24](https://github.com/ROCmSoftwarePlatform/rocFFT/releases/tag/rocm-5.7.1) |
| rocm-cmake | [0.10.0](https://github.com/RadeonOpenCompute/rocm-cmake/releases/tag/rocm-5.7.1) |
| rocPRIM | [2.13.1](https://github.com/ROCmSoftwarePlatform/rocPRIM/releases/tag/rocm-5.7.1) |
| rocRAND | [2.10.17](https://github.com/ROCmSoftwarePlatform/rocRAND/releases/tag/rocm-5.7.1) |
| rocSOLVER | [3.23.0](https://github.com/ROCmSoftwarePlatform/rocSOLVER/releases/tag/rocm-5.7.1) |
| rocSPARSE | [2.5.4](https://github.com/ROCmSoftwarePlatform/rocSPARSE/releases/tag/rocm-5.7.1) |
| rocThrust | [2.18.0](https://github.com/ROCmSoftwarePlatform/rocThrust/releases/tag/rocm-5.7.1) |
| rocWMMA | [1.2.0](https://github.com/ROCmSoftwarePlatform/rocWMMA/releases/tag/rocm-5.7.1) |
| Tensile | [4.38.0](https://github.com/ROCmSoftwarePlatform/Tensile/releases/tag/rocm-5.7.1) |

#### hipSOLVER 1.8.2

hipSOLVER 1.8.2 for ROCm 5.7.1

##### Fixed

- Fixed conflicts between the hipsolver-dev and -asan packages by excluding
  hipsolver_module.f90 from the latter
