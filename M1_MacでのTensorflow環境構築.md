# M1 MacでのTensorflow環境構築

1. Miniforgeのインストール
```Bash
wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh
chmod +x Miniforge3-MacOSX-arm64.sh
sh Miniforge3-MacOSX-arm64.sh
#起動時にbase環境で起動するのをoffにする(任意
conda config --set auto_activate_base false
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

## Miniforgeのアンインストール

```Bash
rm -rf $(conda info --base)
rm -rf ~/.conda

vim ~/.bashrc
'''
以下で囲まれた部分の記述を削除
# >>> conda initialize >>>
# <<< conda initialize <<<
'''
```
