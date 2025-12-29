# private-dataset-Help
The *Help dataset* is specifically constructed for intent recognition research. Derived from stratified sampling of three-year municipal hotline service data across 13 cities, it undergoes rigorous data cleaning and expert review, ultimately comprising 81,820 samples categorized into 600 intent classes.

Specifically, stratified sampling is employed to mitigate sampling bias in intent recognition benchmark datasets, ensuring representativeness across demographic, geographical, and scenario dimensions. Geographically, the sampling covers 13 cities to avoid over-representation of a single urban environment, enabling the dataset to reflect the diverse service needs of residents in different regions. Temporally, the three-year data collection window encompasses holidays, seasonal transitions, and peak periods of urban service demand, addressing the common limitation of insufficient intent representation in short-term datasets and capturing time-varying diverse intent patterns. Beyond capturing heterogeneous user needs across populations, the dataset covers common daily-life scenarios, achieving fine-grained intent coverage.

To ensure data quality, a rigorous two-stage data processing and review pipeline is designed:

**Stage 1: Hybrid Anomaly Data Processing (Rule-Driven + Statistical Methods)**

- Outlier Removal: 2,137 samples significantly deviating from normal patterns are eliminated using the Interquartile Range (IQR) method and domain-specific rules.
- Missing Value Handling: Mode imputation is applied to categorical variables with missing fields, while 892 records lacking critical information are excluded.
- Invalid Sample Filtering: 1,563 invalid samples are removed, including duplicates (detected via text embedding cosine similarity > 0.95), spam content, non-service-related conversations, and incomplete sentences.
  
**Stage 2: Manual Secondary Verification**

Five annotators with over two years of relevant experience review all cleaned samples. Each sample is independently annotated by two annotators to verify three key aspects:

- Semantic validity of the query (i.e., whether the service request is clearly expressed);
- Accuracy of intent labels (i.e., consistency between labels assigned during data collection and users’ true intentions);
- Contextual completeness (i.e., whether the provided context is sufficient for intent determination). Disagreements among annotators are resolved through group discussions moderated by a senior annotator with five years of experience.

Following the aforementioned preprocessing and verification procedures, the final Help dataset contains 81,820 valid samples, each labeled with a unique intent tag. These tags form a classification system encompassing 600 distinct intent categories.

Due to privacy considerations for users, the full dataset is not publicly accessible. De-identified samples can be obtained by contacting the corresponding author, with usage limited to academic research and replication studies.
