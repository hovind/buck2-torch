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
    url = "https://files.pythonhosted.org/packages/a6/f8/dae3421624fcc87a89d42e1898a798bc7ff72c61f38973a65d60df8f124c/safetensors-0.5.3-cp38-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl",
    sha256 = "cead1fa41fc54b1e61089fa57452e8834f798cb1dc7a09ba3524f1eb08e0317a",
)

remote_file(
    name = "tokenizers-download",
    url = "https://files.pythonhosted.org/packages/22/06/69d7ce374747edaf1695a4f61b83570d91cc8bbfc51ccfecf76f56ab4aac/tokenizers-0.21.0-cp39-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl",
    sha256 = "e84ca973b3a96894d1707e189c14a774b701596d579ffc7e69debfc036a61a04",
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
    url = "https://files.pythonhosted.org/packages/4b/27/285a8cf12bd7cd71f9f211a968516b07dcffed3ef0be585c6e823675ab91/torch-2.7.0-cp313-cp313-manylinux_2_28_x86_64.whl",
    sha256 = "9b52347118116cf3dff2ab5a3c3dd97c719eb924ac658ca2a7335652076df708",
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
    name = "tokenizers",
    binary_src = ":tokenizers-download",
)

prebuilt_python_library(
    name = "transformers",
    binary_src = ":transformers-download",
    deps = [
        ":huggingface-hub",
        ":regex",
        ":safetensors",
        ":tokenizers",
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
        "//nvidia:nvidia",
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
