# predictHD

predictHD is a predictive model designed to identify hard drive (HDD) failures before they occur. By leveraging advanced data processing techniques and machine learning models, predictHD offers enhanced prediction accuracy and actionable insights for data center maintenance. This project utilizes a comprehensive dataset from BackBlaze, spanning from 2013 to 2023.

## Project Structure

### 1. Data Processing

#### Scripts:

1. **zscore.py**: Normalizes the dataset using z-score normalization to standardize the values.
2. **parquet.py**: Converts raw data into Parquet format for efficient storage and retrieval.
3. **splitting_into_contiguous_chunks.py**: Segments the data into contiguous chunks for more manageable processing.
4. **vectorized_to_unix_timestamp.py**: Converts vectorized date-time data into Unix timestamps.
5. **vectorizing_contiguous_chunks.py**: Vectorizes the text data within the contiguous chunks.
6. **bigquery.py**: Uploads processed data to Google BigQuery for further analysis.
7. **cae_cnn_mixtral.py**: Constructs a Convolutional Autoencoder (CAE) and integrates it with the Mixtral transformer model for predictive analytics.

### 2. Data Details

- **Dataset**: BackBlaze HDD Failure Data
- **File**: `combined_data.parquet` stored in Google Cloud Storage bucket `backblazehd_parquet_data`
- **BigQuery Details**: 
  - Project ID: `backblazehd`
  - Dataset: `hdd_failure_data`
  - Table: `failure_logs`

### 3. Model Architecture

The predictive model is built using a hybrid approach, combining Convolutional Autoencoder (CAE) and the Mixtral transformer model. This configuration helps in accurately predicting HDD failures by analyzing historical failure patterns and current operational metrics.

### 4. Usage

#### Requirements

- Python 3.7+
- Libraries: `pandas`, `numpy`, `tensorflow`, `scikit-learn`, `google-cloud-bigquery`
- Google Cloud SDK

#### Steps

1. **Data Normalization**: Run `zscore.py` to normalize the dataset.
2. **Data Conversion**: Use `parquet.py` to convert data into Parquet format.
3. **Data Segmentation**: Execute `splitting_into_contiguous_chunks.py` to split the dataset.
4. **Timestamp Conversion**: Run `vectorized_to_unix_timestamp.py` to convert dates.
5. **Data Vectorization**: Use `vectorizing_contiguous_chunks.py` for vectorizing the chunks.
6. **Data Upload**: Upload processed data to BigQuery using `bigquery.py`.
7. **Model Training**: Train the predictive model using `cae_cnn_mixtral.py`.

### 5. Configuration

Ensure the `config.json` file contains the correct model configuration details. This file should be utilized in the Google Colab script without logging into Hugging Face.

### 6. Example Query

To identify hard drives that failed on a specific date (e.g., December 21, 2022), update the `cae_cnn_mixtral.py` script accordingly and run the prediction engine.

### 7. Results

The predictive model demonstrated the following performance metrics:

- **F1 Score**: 0.85
- **Precision**: 0.83
- **Recall**: 0.87
- **Accuracy**: 0.88

### 8. Contributions

- **Author**: Aniruddha Prabhash Chakravarty ([aniruddhaprabhash.chakravarty@sjsu.edu](mailto:aniruddhaprabhash.chakravarty@sjsu.edu))
- **Collaborator**: Abhishek Bhardwaj ([abhishek.bhardwaj@sjsu.edu](mailto:abhishek.bhardwaj@sjsu.edu))
- **Supervisor**: Dr. Saptarshi Sengupta

### 9. Contact

For any queries or further information, please contact Aniruddha Prabhash Chakravarty via [aniruddhaprabhash.chakravarty@sjsu.edu](mailto:aniruddhaprabhash.chakravarty@sjsu.edu).

### 10. License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

predictHD exemplifies cutting-edge research in predictive analytics for HDD failures, offering robust solutions for enhancing data center reliability and efficiency.
