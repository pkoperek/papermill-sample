## What is that?

Papermill is a tool which allows to parametrize, execute and analyze Jupyter
notebooks.

* How can you create a parameterized notebook?
  * [Doc link](https://papermill.readthedocs.io/en/latest/usage-parameterize.html#notebook)
* How does papermill work?
  ```
  How parameters work?

  The parameters cell is assumed to specify default values which may be
  overridden by values specified at execution time.

  * papermill inserts a new cell tagged injected-parameters immediately after the
    parameters cell
  * injected-parameters contains only the overridden parameters
  * subsequent cells are treated as normal cells, even if also tagged parameters
  * if no cell is tagged parameters, the injected-parameters cell is inserted at
    the top of the notebook

  One caveat is that a parameters cell may not behave intuitively with
  inter-dependent parameters.
  ```
  [Source](https://papermill.readthedocs.io/en/latest/usage-parameterize.html#how-parameters-work)

## Running Papermill sample

* The sample notebook is called `SampleParametrized.ipynb`
* Run the notebook through papermill: `papermill -p parameter1 3.14 SampleParametrized.ipynb SampleParametrized_Executed.ipynb`
* This creates (renders) the `SampleParametrized_Executed.ipynb` which is
  basically the input notebook with additional cell marked with
  `injected-parameters` tag.

## Env setup with pipenv

* Initialized with: `pipenv --python 3.8`
* Turn on the shell: `pipenv shell`
* Unfortunately due to conflicts in the deps, the lock file could not be
  created :(
