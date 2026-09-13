# Rainfall Nowcasting Model Comparison

This project evaluates short-horizon rainfall forecasting methods for Chennai using 30-minute IMERG rainfall data from 2021 through 2025.

## Study design

- **Training:** 2021-2023
- **Validation:** 2024
- **Final testing:** 2025
- **Methods:** Persistence, classical time-series forecasting, CNN-LSTM, and a Persistence/CNN-LSTM hybrid
- **Metrics:** MAE, RMSE, and R²

The validation period is used to select the hybrid ensemble weight. That weight is then frozen before generating predictions for the 2025 test period, avoiding test-set tuning.

## Notebooks

- [`Rainfall_nowcasting_model_comparison.ipynb`](Rainfall_nowcasting_model_comparison.ipynb) compares the forecasting approaches and evaluates performance across Chennai's seasonal rainfall regimes.
- [`Hybrid_persistence_and_cnn_lstm.ipynb`](Hybrid_persistence_and_cnn_lstm.ipynb) loads existing models, searches hybrid weights from 0% to 100%, and compares the selected hybrid against Persistence and CNN-LSTM.

## Requirements

The notebooks use Python packages including:

- NumPy
- pandas
- Matplotlib
- scikit-learn
- TensorFlow

The notebooks are designed for Google Colab and load the dataset and saved models from Google Drive. Update the referenced Drive paths and ensure the required data/models are available before running the cells.

## Running the project

1. Open a notebook in Google Colab or a Jupyter environment.
2. Install or enable the required Python packages.
3. Mount Google Drive when prompted and update any dataset/model paths.
4. Run the cells in order.

The notebooks do not retrain the CNN-LSTM model during hybrid evaluation; they use the existing saved model and generate validation and test predictions.