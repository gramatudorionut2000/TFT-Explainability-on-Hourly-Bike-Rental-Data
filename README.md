# TFT-Explainability-on-Hourly-Bike-Rental-Data
Code, model checkpoints and requirements for a study of the Temporal Fusion Transformer's built-in interpretability components, trained on the UCI Capital Bikeshare hourly dataset (2011–2012) using the Darts implementation.

The analysis covers variable selection across the encoder and decoder, the temporal distribution of attention and its dependence on the prediction origin, quantile forecast calibration, and model behaviour during Hurricane Sandy, a rare event contained in the test period.

Attention patterns from a single forecast window did not survive averaging across forecast origins, and the averaged pattern remained ambiguous until the prediction start hour was varied.

Contents

tft_experiments.ipynb  : pre-processing, training, explainability analysis, figures
checkpoints/ : trained model weights
requirements.txt : dependencies

Setup: three-way chronological split (train to 2012-06-30, validation to 2012-09-30, test to 2012-12-31), 168-hour context, 24-hour horizon, quantile regression at the 5th–95th percentiles. Observed weather is used as past covariates; calendar features as future covariates.

Accompanying article: https://medium.com/@grama.tudorionut/variable-importance-attention-and-explainable-forecasting-with-tft-72f795a2e2e3
