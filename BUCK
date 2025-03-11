# A list of available rules and their signatures can be found here: https://buck2.build/docs/prelude/globals/

remote_file(
    name = "tdqm-download",
    url = "https://files.pythonhosted.org/packages/d0/30/dc54f88dd4a2b5dc8a0279bdd7270e735851848b762aeb1c1184ed1f6b14/tqdm-4.67.1-py3-none-any.whl",
    sha256 = "26445eca388f82e72884e0d580d5464cd801a3ea01e63e5601bdff9ba6a48de2",
)

remote_file(
    name = "filelock-download",
    url = "https://files.pythonhosted.org/packages/89/ec/00d68c4ddfedfe64159999e5f8a98fb8442729a63e2077eb9dcd89623d27/filelock-3.17.0-py3-none-any.whl",
    sha256 = "533dc2f7ba78dc2f0f531fc6c4940addf7b70a481e269a5a3b93be94ffbe8338",
)

remote_file(
    name = "huggingface-hub-download",
    url = "https://files.pythonhosted.org/packages/40/0c/37d380846a2e5c9a3c6a73d26ffbcfdcad5fc3eacf42fdf7cff56f2af634/huggingface_hub-0.29.3-py3-none-any.whl",
    sha256 = "0b25710932ac649c08cdbefa6c6ccb8e88eef82927cacdb048efb726429453aa",
)

remote_file(
    name = "regex-download",
    url = "https://files.pythonhosted.org/packages/ed/e3/c446a64984ea9f69982ba1a69d4658d5014bc7a0ea468a07e1a1265db6e2/regex-2024.11.6-cp313-cp313-musllinux_1_2_x86_64.whl",
    sha256 = "4f51f88c126370dcec4908576c5a627220da6c09d0bff31cfa89f2523843316d",
)

remote_file(
    name = "safetensors-download",
    url = "https://files.pythonhosted.org/packages/40/ad/2b113098e69c985a3d8fbda4b902778eae4a35b7d5188859b4a63d30c161/safetensors-0.5.3-cp38-abi3-musllinux_1_2_x86_64.whl",
    sha256 = "37f1521be045e56fc2b54c606d4455573e717b2d887c579ee1dbba5f868ece04",
)

remote_file(
    name = "transformers-download",
    url = "https://files.pythonhosted.org/packages/20/37/1f29af63e9c30156a3ed6ebc2754077016577c094f31de7b2631e5d379eb/transformers-4.49.0-py3-none-any.whl",
    sha256 = "6b4fded1c5fee04d384b1014495b4235a2b53c87503d7d592423c06128cbbe03",
)

remote_file(
    name = "typing-extensions-download",
    url = "https://files.pythonhosted.org/packages/26/9f/ad63fc0248c5379346306f8668cda6e2e2e9c95e01216d2b8ffd9ff037d0/typing_extensions-4.12.2-py3-none-any.whl",
    sha256 = "04e5ca0351e0f3f85c6853954072df659d0d13fac324d0072316b67d7794700d",
)

remote_file(
    name = "torch-download",
    url = "https://files.pythonhosted.org/packages/e5/35/0c52d708144c2deb595cd22819a609f78fdd699b95ff6f0ebcd456e3c7c1/torch-2.6.0-cp312-cp312-manylinux1_x86_64.whl",
    sha256 = "2bb8987f3bb1ef2675897034402373ddfc8f5ef0e156e2d8cfc47cacafdda4a9",
)

prebuilt_python_library(
    name = "tdqm",
    binary_src = ":tdqm-download",
)

prebuilt_python_library(
    name = "filelock",
    binary_src = ":filelock-download",
)

prebuilt_python_library(
    name = "huggingface-hub",
    binary_src = ":huggingface-hub-download",
    deps = [
        ":filelock",
        ":tdqm",
    ],
)

prebuilt_python_library(
    name = "regex",
    binary_src = ":regex-download",
)

prebuilt_python_library(
    name = "safetensors",
    binary_src = ":safetensors-download",
)

prebuilt_python_library(
    name = "transformers",
    binary_src = ":transformers-download",
    deps = [
        ":huggingface-hub",
        ":regex",
        ":safetensors",
    ],
)

prebuilt_python_library(
    name = "typing-extensions",
    binary_src = ":typing-extensions-download",
)

prebuilt_python_library(
    name = "torch",
    binary_src = ":torch-download",
    deps = [
        ":typing-extensions",
        "//cudnn:nvidia-cudnn",
        "//cusparse:nvidia-cusparse",
    ],
)

python_binary(
    name = "main",
    main = "main.py",
    deps = [
        ":transformers",
        ":torch",
    ],
)
