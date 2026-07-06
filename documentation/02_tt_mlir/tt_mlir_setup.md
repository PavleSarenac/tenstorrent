# [tt_mlir](https://github.com/tenstorrent/tt-mlir) setup on [Wormhole n300](https://tenstorrent.com/hardware/cards)

![Wormhole n300](./images/wormhole_n300.png)

## Step 1

```bash
sudo apt install -y git clang clang-20 cmake ninja-build pip python3.12-venv
```

## Step 2

```bash
clang --version
```

### Expected output (14 <= version <= 18 for [tt-mlir](https://github.com/tenstorrent/tt-mlir))

![clang version output](./images/clang_version_output.png)

## Step 3

```bash
clang-20 --version
```

### Expected output (version >= 20 for [tt-mlir](https://github.com/tenstorrent/tt-mlir) with `-DTTMLIR_ENABLE_RUNTIME=ON`)

![clang-20 version output](./images/clang_20_version_output.png)

## Step 4

```bash
cmake --version
```

### Expected output (version >= 3.24 for [tt-mlir](https://github.com/tenstorrent/tt-mlir))

![cmake version output](./images/cmake_version_output.png)

## Step 5

```bash
ninja --version
```

### Expected output (version >= 1.11.1 for [tt-mlir](https://github.com/tenstorrent/tt-mlir))

![ninja version output](./images/ninja_version_output.png)

## Step 6

```bash
python3.12 --version
```

### Expected output (version == 3.12.x for [tt-mlir](https://github.com/tenstorrent/tt-mlir))

![python 3.12 version output](./images/python_3_12_version_output.png)

## Step 7

```bash
deactivate 2>/dev/null
```

## Step 8

```bash
unset VIRTUAL_ENV PYTHON_ENV_DIR PYTHONPATH
```

## Step 9

```bash
hash -r
```

## Step 10

```bash
echo $VIRTUAL_ENV $PYTHON_ENV_DIR $PYTHONPATH
```

### Expected output: (empty)

## Step 11

```bash
git clone https://github.com/tenstorrent/tt-mlir.git
```

## Step 12

```bash
cd tt-mlir
```

## Step 13

```bash
export TTMLIR_TOOLCHAIN_DIR=$HOME/ttmlir-toolchain/
```

## Step 14

```bash
mkdir -p "${TTMLIR_TOOLCHAIN_DIR}"
```

## Step 15

```bash
cmake -B env/build env -DCMAKE_C_COMPILER=clang -DCMAKE_CXX_COMPILER=clang++
```

## Step 16

```bash
cmake --build env/build
```

## Step 17

```bash
rm -rf /home/psarenac/tt-mlir/env/build
```

### Replace `/home/psarenac/tt-mlir` with the path to your cloned tt-mlir repo

## Step 18

```bash
source env/activate
```

## Step 19

```bash
cmake -G Ninja -B build \
    -DCMAKE_C_COMPILER=clang \
    -DCMAKE_CXX_COMPILER=clang++ \
    -DTTMLIR_ENABLE_RUNTIME=ON \
    -DTT_RUNTIME_ENABLE_PERF_TRACE=ON \
    -DTTMLIR_ENABLE_OPMODEL=ON \
    -DTT_RUNTIME_DEBUG=ON \
    -DCMAKE_CXX_COMPILER_LAUNCHER=ccache
```

## Step 20

```bash
cmake --build build
```

## Step 21

```bash
cmake --build build -- check-ttmlir
```

### Expected output

![check tt-mlir output](./images/check_tt_mlir_output.png)

## Step 22

```bash
pre-commit install
```

## Step 23

```bash
cmake --build build -- clang-tidy
```

## Step 24

```bash
cmake --build build -- clang-tidy-ci
```

## Optional Documentation Generation  

## Step 25

```bash
cd $HOME
```

## Step 26

```bash
curl -L https://github.com/rust-lang/mdBook/releases/download/v0.5.3/mdbook-v0.5.3-x86_64-unknown-linux-gnu.tar.gz -o mdbook.tar.gz
```

## Step 27

```bash
tar xzf mdbook.tar.gz
```

## Step 28

```bash
mkdir -p $HOME/bin
```

## Step 29

```bash
mv $HOME/mdbook $HOME/bin/mdbook
```

## Step 30

```bash
export PATH="$HOME/bin:$PATH
```

## Step 31

```bash
cd tt-mlir
```

## Step 32

```bash
source env/activate
```

## Step 33

```bash
cmake --build build -- docs
```

## Step 34

```bash
mdbook serve build/docs
```
