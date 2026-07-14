# Testing

## [tt-mlir/test/python/golden/ttir_ops/data_movement/test_data_movement.py](https://github.com/tenstorrent/tt-mlir/blob/main/test/python/golden/ttir_ops/data_movement/test_data_movement.py)

### Run `test_slice` tests

```bash
cd tt-mlir
source env/activate
pytest test/python/golden/ttir_ops/data_movement/test_data_movement.py::test_slice -v 2>&1 | tee generated/test_slice.log
```

## [tt-mlir/test/ttmlir/Dialect/TTIR/data_movement/slice/slice_tests_negative.mlir](https://github.com/tenstorrent/tt-mlir/blob/main/test/ttmlir/Dialect/TTIR/data_movement/slice/slice_tests_negative.mlir)

### Run `slice_tests_negative.mlir` tests

```bash
cd tt-mlir
source env/activate
llvm-lit test/ttmlir/Dialect/TTIR/data_movement/slice/slice_tests_negative.mlir -v 2>&1 | tee generated/slice_tests_negative_mlir.log
```
