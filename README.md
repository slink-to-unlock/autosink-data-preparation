# Data Preparation for Autosink Project

[🇬🇧](README.md) | [🇰🇷](README.kr.md) | [🇨🇳](README.zh-CN.md)

The data preparation component is originally responsible for fetching raw data. However, in our `autosink` project system, there is a feature store, so data preparation does not fetch raw data. Instead, it is considered as data preprocessing, such as image augmentation, which should be done in data preparation. The result of data preprocessing will actually be stored in the feature store. This package first explores the results of preprocessing in the feature store, and if it does not exist, it performs data preprocessing and passes the input to downstream components.

## Features

- [ ] Return the dataset after performing data preprocessing
- [ ] Prioritize exploring the feature store before performing data preprocessing and returning the result

# Environment

The environment is based on MacOS and Linux.

## `Makefile`

The `Makefile` has the following functions.

### `make lint`

- To use the `.vscode` settings, install the `pylint` extension.
- Overrides the options specified in the `pyproject.toml` file to lint the code based on the default settings of the linter.

### `make format`

- The formatter uses google's `yapf`.
- Overrides the options specified in the `pyproject.toml` file to format the code based on the default settings of the `yapf` formatter.
- To use the `.vscode` settings, install the `yapf` extension.

### `make test`

- Uses `unittest` for testing.
- Supports both `test_*.py` and `*_test.py` patterns.
- The test file must be connected to `__init__.py` up to the location of the test file.

### `make publish`

- Write the `~/.pypirc` file as follows.
    ```
    [pypi]
    username = __token__
    password = pypi-어쩌고저쩌고 # Write your personal API token.
    ```
- Running this command will push the package to the PyPI public registry using `flit`.
- The package uploaded under the alias `myproject` will be available for anyone worldwide to install and use with `python3 -m pip install myproject`.