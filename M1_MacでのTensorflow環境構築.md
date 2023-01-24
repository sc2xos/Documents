# M1 MacでのTensorflow環境構築

1. Miniforgeのインストール
```Bash
chmod +x ~/Downloads/Miniforge3-MacOSX-arm64.sh
sh ~/Downloads/Miniforge3-MacOSX-arm64.sh
source ~/miniforge3/bin/activate
```

2. Tensorflow(Metal)のインストール
```Bash
conda create -n tensorflow python=3.8
conda activate tensorflow
conda install -c apple tensorflow-deps
python -m pip install tensorflow-macos==2.7.0
python -m pip install tensorflow-metal
```

3. インストール確認
```Bash
python -c 'import tensorflow; print(tensorflow.__version__)'
```
