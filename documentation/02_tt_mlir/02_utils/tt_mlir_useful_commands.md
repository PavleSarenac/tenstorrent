# Testing

## [tt-mlir/test/python/golden/ttir_ops/data_movement/test_data_movement.py](https://github.com/tenstorrent/tt-mlir/blob/main/test/python/golden/ttir_ops/data_movement/test_data_movement.py)

### Run `tt-mlir/test/python/golden/ttir_ops/data_movement/test_data_movement.py::test_slice` tests

```bash
cd tt-mlir
```

```bash
source env/activate
```

```bash
pytest test/python/golden/ttir_ops/data_movement/test_data_movement.py::test_slice -v 2>&1 | tee generated/test_slice.log
```

## [tt-mlir/test/ttmlir/Dialect/TTIR/data_movement/slice/slice_tests_negative.mlir](https://github.com/tenstorrent/tt-mlir/blob/main/test/ttmlir/Dialect/TTIR/data_movement/slice/slice_tests_negative.mlir)

### Run `tt-mlir/test/ttmlir/Dialect/TTIR/data_movement/slice/slice_tests_negative.mlir` tests

```bash
cd tt-mlir
```

```bash
source env/activate
```

```bash
llvm-lit test/ttmlir/Dialect/TTIR/data_movement/slice/slice_tests_negative.mlir -v 2>&1 | tee generated/slice_tests_negative_mlir.log
```

## [tt-mlir/test/ttmlir/Dialect/TTIR/data_movement/slice/slice_tests_positive.mlir](https://github.com/tenstorrent/tt-mlir/blob/main/test/ttmlir/Dialect/TTIR/data_movement/slice/slice_tests_positive.mlir)

### Run `slice_tests_positive.mlir` tests

```bash
cd tt-mlir
```

```bash
source env/activate
```

```bash
llvm-lit test/ttmlir/Dialect/TTIR/data_movement/slice/slice_tests_positive.mlir -v 2>&1 | tee generated/slice_tests_positive_mlir.log
```

## [tt-mlir/test/ttmlir/Dialect/TTNN/simple_slice.mlir](https://github.com/tenstorrent/tt-mlir/blob/main/test/ttmlir/Dialect/TTNN/simple_slice.mlir)

### Run `tt-mlir/test/ttmlir/Dialect/TTNN/simple_slice.mlir` tests

```bash
cd tt-mlir
```

```bash
source env/activate
```

```bash
llvm-lit test/ttmlir/Dialect/TTNN/simple_slice.mlir -v 2>&1 | tee generated/simple_slice_ttnn.log
```
