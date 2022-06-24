

# FAST_TFRS recommendation engine

`fast_tfrs` is a deep learning recommendation engine for fast experimentations and productionization.

Built on Google Tensorflow Recommendation Systems [tfrs](https://www.tensorflow.org/recommenders), fast_tfrs aims to be:

- easy-to-use: no boiler-plate coding required, simple API to follow
- easy-to-rebuild (custom): modules are lego-like, ready to be mixed and match
- end-to-end: input raw data output predictions
- stable and scalable for production

To be specific, I contrast the feature differences between `tfrs` and `fast_tfrs` as follow:

- feature encoding
  - `tfrs`: requires writting code to encode each feature used in the recommendation, making it not scalable and error-prone in case we have many features
  - `fast_tfrs`: automates the encoding for all selected features, making it a bleeze for large scale experimentations.

- feature dtype
  - `tfrs`: requires expertise to encode feature of different data-types, include cnt(continuous feature), cat(categorical feature), txt(text feature), img (image feature), dt(datetime feature)
  - `fast_tfrs`: provides helpers to automatically separate features of different data-types and corresponding encoders for each type.

- feature selection
  - `tfrs`: no tools provided
  - `fast_tfrs`: provides tools to select relevant features, at this release include L1, VSN

- feature crossing
  - `tfrs`: no tools provided
  - `fast_tfrs`: provides tools to feature crossing (i.e. feature interactions), at this release include DeepCrossLayer, vsn_DeepCrossLayer

- multitask
  - `tfrs`: provides 2 tasks -- ranking and retrieval
  - `fast_tfrs`: provides 3 tasks -- ranking, retrieval and classification (imbalanced multiclass classification)

`fast_tfrs` is under active development and welcomes community contribution. For recent updates, please visit https://github.com/wjlgatech/fast_tfrs
