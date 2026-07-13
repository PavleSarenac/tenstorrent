# Testing

## [tt-mlir/test/python/golden/ttir_ops/data_movement/test_data_movement.py](https://github.com/tenstorrent/tt-mlir/blob/main/test/python/golden/ttir_ops/data_movement/test_data_movement.py)

### Run `test_slice` tests

```bash
cd tt-mlir
source env/activate
pytest test/python/golden/ttir_ops/data_movement/test_data_movement.py::test_slice -v 2>&1 | tee generated/test_slice.log
```
