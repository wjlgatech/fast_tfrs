

# FAST_TFRS recommendation engine

`fast_tfrs` is a deep learning recommendation engine for fast experimentations and productionization.


## Why fast_tfrs

Built on Google Tensorflow Recommendation Systems [tfrs](https://www.tensorflow.org/recommenders), fast_tfrs aims to be:

- easy-to-use: no boiler-plate coding required, simple API to follow
- easy-to-rebuild (custom): modules are lego-like, ready to be mixed and match
- end-to-end: input raw data output predictions
- stable and scalable for production

To be specific, I contrast the feature differences between `tfrs` and `fast_tfrs` as follow:

- feature encoding
  - `tfrs` requires writting code to encode each feature used in the recommendation, making it not scalable and error-prone in case we have many features
  - `fast_tfrs` automates the encoding for all selected features, making it a bleeze for large scale experimentations.

- feature dtype
  - `tfrs`: requires expertise to encode feature of different data-types, include cnt(continuous feature), cat(categorical feature), txt(text feature), img (image feature), dt(datetime feature)
  - `fast_tfrs`: provides helpers to automatically separate features of different data-types and corresponding encoders for each type.

- feature selection
  - `tfrs` provides no tools
  - `fast_tfrs` provides tools to select relevant features, at this release include L1, VSN

- feature crossing
  - `tfrs` provides no tools 
  - `fast_tfrs` provides tools to feature crossing (i.e. feature interactions), at this release include DeepCrossLayer, vsn_DeepCrossLayer

- multitask
  - `tfrs` provides 2 tasks -- ranking and retrieval
  - `fast_tfrs` provides 3 tasks -- ranking, retrieval and classification (imbalanced multiclass classification)

`fast_tfrs` is under active development and welcomes community contribution. For recent updates, please visit https://github.com/wjlgatech/fast_tfrs

## Installation
```python
url = f"git+https://github.com/wjlgatech/fast_tfrs.git"
!pip install --upgrade {url}
```

## Quick Start

- Check out [fast_tfrs_quickstart.ipynb](https://github.com/wjlgatech/fast_tfrs/blob/master/examples/fast_tfrs_quickstart.ipynb)

- More details: [fast_tfrs_all_code_walkthrough.ipynb](https://github.com/wjlgatech/fast_tfrs/blob/master/examples/fast_tfrs_all_code_walkthrough.ipynb)


## Known Issues

As you will see in [fast_tfrs_all_code_walkthrough.ipynb](https://github.com/wjlgatech/fast_tfrs/blob/master/examples/fast_tfrs_all_code_walkthrough.ipynb): 

- "StopIteration: Queue is empty, no more objects to retrieve" in section **Get the best fast_tfrs model by Bayesian tuning
**

- "TuneError: ('Trials did not complete'...)" in section **FLAML + Ray tuning**

- "feature importances plot lacks symetric" in function plot_cross_feature_importances(...) in section **Model understanding**

- The integration of `classification_task`  with `retrieval_task` and `rating_task` in section **3-task w. L1/VSN features selection**

Please let me know if you have any idea on how to fix them.
