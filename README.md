# Election Prediction 2029: Haryana Assembly Forecast

## Description
This project utilizes machine learning to forecast the constituency-wise winners and overall seat tally for the upcoming 2029 Haryana Legislative Assembly elections. By analyzing historical voting data from the 2019 and 2024 elections, the model identifies underlying patterns between vote shares and winning parties to simulate potential outcomes for 2029. 

## Methodology
The prediction pipeline is structured into the following key phases:

1. **Data Processing & Alignment:** Loads constituency-wise election data, cleaning column names and removing duplicate entries. Filters and aligns the dataset to ensure only constituencies that participated in both the 2019 and 2024 elections are included in the analysis (totaling 87 constituencies).
2. **Feature Engineering:** Constructs a consolidated feature set combining the percentage vote shares of major parties (BJP, CONGRESS, BSP, INLD, OTHERS) from both 2019 and 2024.
3. **Model Training:** Trains a Machine Learning classification model where the inputs are the combined historical vote shares (2019 + 2024) and the target variable is the winning party in 2024. 
4. **2029 Election Simulation:** Applies a hypothetical **3% swing (increase)** to the 2024 vote shares to simulate the political landscape for the 2029 elections. Feeds this simulated data into the trained model to predict the 2029 winner for each individual constituency.

## Model Details
* **Algorithm:** `RandomForestClassifier` (from `scikit-learn`)
* **Random State:** 42 (for reproducibility)
* **Why Random Forest?** Random Forest is an ensemble learning method that operates by constructing multiple decision trees during training. It is highly effective for this type of tabular data, as it naturally handles non-linear relationships and interactions between the vote shares of different political parties, reducing the risk of overfitting compared to a single decision tree.

## Results & Insights
Based on the 3% simulated vote swing applied to the 2024 baseline, the Random Forest model predicts the following seat distribution for the 87 analyzed constituencies in 2029:

| Party | Predicted Seats Won |
| :--- | :--- |
| **BJP** | 41 |
| **CONGRESS** | 34 |
| **OTHERS** | 11 |
| **INLD** | 1 |

### Key Takeaway
* **No Clear Majority:** The magic number for a clear majority in the Haryana assembly is 46 seats. According to this simulation, the leading party (BJP) secures 41 seats, falling short of the majority threshold. This outcome indicates a highly competitive election resulting in a potential **hung assembly**, where smaller parties and independent candidates ("OTHERS") would play a crucial role in coalition building.
